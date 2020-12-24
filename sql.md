查询平均运行时间大于10的任务

select id, name, a.avg from job join (select job_id, avg(l.end_time - l.start_time) as avg from log l group by job_id) a on a.job_id = job.id

第二高的薪水

select distinct Salary as SecondHighestSalary from Employee order by Salary DESC limit 1,1

第N高的薪水

CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT
BEGIN
      set N=N-1;
  RETURN (
      # Write your MySQL query statement below.
      select a.Salary from  (select distinct Salary from Employee order by Salary DESC limit N,1) a
  );
END

分数排名

select Score, (select count(distinct score) from Scores where score >= d.score ) as Rank from Scores d order by Score desc

薪水大于经理的员工

select Name as Employee from Employee a where Salary > (select Salary from Employee where Id = a.ManagerId)

查找重复的电子邮箱

select Email from Person group by Email having count(Email) >=2
