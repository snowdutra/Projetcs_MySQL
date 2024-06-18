use carloca;

Select *  from loc_funcionario;

-- Quem ganha mais que a Mari --
Select Vl_Salario from loc_funcionario where Cd_Func = 5;
Select Nm_func, Vl_Salario from loc_funcionario where Vl_Salario >= 7146; 

-- Solução Programada (Recorrente)
Select Nm_func, Vl_Salario 
	from loc_funcionario 
	where Vl_salario >= ( Select Vl_salario 
							from loc _funcionario
                            where cd_func = 5);
    
-- Solução Gui --
Select Vl_Salario from loc_funcionario where Nm_func like '%Mari%'; 
Select Nm_func, Vl_Salario 
	from loc_funcionario 
	where Vl_salario >= ( Select Vl_salario 
							from loc _funcionario 
                            where Nm_func
                            like '%Mari%');

-- Quando não busca pela PK pode trazer mais de um registro --
Select Nm_func, Vl_Salario 
	from loc_funcionario 
	where Vl_salario >= ( Select Vl_salario 
							from loc _funcionario 
							where Nm_func 
                            like '%Adriana%');

-- Quem ganha mais que a média salarial da carloca -- 
Select avg(Vl_salario) from loc_funcionario;
Select nm_func, Vl_Salario
	from loc_funcionario 
    where Vl_salario > (Select avg(Vl_salario)
						from loc_funcionario);
    
-- Quem ganha mais que a média salarial do departamento com a menor média salarial da Carloca --
Select Nm_Func, Vl_salario
	from loc_funcionario 
	where Vl_salario > any (Select avg(Vl_salario) 
						from loc_funcionario 	
                        group by cd_depto);
                        
-- Quem ganha mais que a média salarial de todos os departamentos com a menor média salarial da Carloca --

Select Nm_Func, Vl_salario
	from loc_funcionario 
	where Vl_salario > all (Select avg(Vl_salario) 
						from loc_funcionario 	
                        group by cd_depto);

Select Nm_func, Nm_depto
	from loc_funcionario f
	inner join loc_depto d on f.cd_depto = d.cd_depto;
    
create view Ana as 
	(Select Nm_func, Nm_depto
		from loc_funcionario f
		inner join loc_depto d on f.cd_depto = d.cd_depto);

Select * from Ana;
