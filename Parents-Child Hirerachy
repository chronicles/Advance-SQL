/**************************************************************
  EXAMPLE : Ancestors
  Find all of Mary's ancestors
**************************************************************/


create table ParentOf(parent text, child text);

insert into ParentOf values ('Alice', 'Carol');
insert into ParentOf values ('Bob', 'Carol');
insert into ParentOf values ('Carol', 'Dave');
insert into ParentOf values ('Carol', 'George');
insert into ParentOf values ('Dave', 'Mary');
insert into ParentOf values ('Eve', 'Mary');
insert into ParentOf values ('Mary', 'Frank');

with recursive
  Ancestor(a,d) as (select parent as a, child as d from ParentOf
                    union
                    select Ancestor.a, ParentOf.child as d
                    from Ancestor, ParentOf
                    where Ancestor.d = ParentOf.parent)
select a from Ancestor where d = 'Mary';

