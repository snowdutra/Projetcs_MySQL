use carloca;

select sum(Vl_Salario), max(Vl_salario), min(Vl_Salario)
	from loc_funcionario;
    
select Vl_Salario
	from loc_funcionario
	order by Vl_Salario; 
    
select Nm_Func, Vl_Salario, cd_depto
	from loc_funcionario
    order by cd_depto, Vl_salario;
    
select sum(Vl_Salario)
	from loc_funcionario
    group by cd_depto;
    
select nm_depto, sum(Vl_Salario)
	from loc_funcionario f
    inner join loc_depto d on f.cd_depto = d.cd_depto
    group by nm_depto
    order by sum(Vl_Salario;

    
-- Mostre a soma de salrios de departamentos com valores acima de 10 mil --

select nm_depto, sum(Vl_Salario)
	from loc_funcionario f
    inner join loc_depto d on f.cd_depto = d.cd_depto
    group by nm_depto
    having sum(Vl_salario) > 10000
    order by sum(Vl_Salario);

    
    -- Mostre somas salariais mas eleimine os salarios abaixo de 7500 --
    
    select nm_depto, sum(Vl_Salario)
	from loc_funcionario f
    inner join loc_depto d on f.cd_depto = d.cd_depto
	where Vl_salario > 7500
    group by nm_depto
    order by sum(Vl_Salario);

    
    -- Mostre as somas salariais dos departamnetos eliminado os 
    -- salarios abaixo de 5000 e valores de soma abaixo de 10000 --
    
     select nm_depto, sum(Vl_Salario)
	from loc_funcionario f
    inner join loc_depto d on f.cd_depto = d.cd_depto
	where Vl_salario > 5000
    group by nm_depto
    having sum(Vl_salario) > 10000
    order by sum(Vl_Salario);

    
-- Quem ganha mais que a Adriana Doretto --
-- Quanto ela ganha? --

Select * from loc_funcionario;
Select Vl_Salario from loc_funcionario where cd_func =4;
Select nm_func, vl_salario
	from loc_funcionario
	where Vl_salario > 7146;
Select nm_func, vl_salario
	from loc_funcionario
	where Vl_salario > (7146);
Select nm_func, vl_salario
	from loc_funcionario
	where Vl_salario > (Select Vl_Salario 
						from loc_funcionario 
						where cd_func =4);

                        
Select avg(Vl_salario)
	from loc_funcionario
    group by cd_depto;
                        
Select nm_func, vl_salario
	from loc_funcionario
	where Vl_salario  in (Select avg(Vl_salario)
						from loc_funcionario
						group by cd_depto);
