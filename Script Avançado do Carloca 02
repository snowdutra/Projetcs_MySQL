use carloca;

-- 1
SELECT Nr_Placa, Nm_Modelo, Nm_Proprietario, desc_cor
	FROM Loc_Veiculo V
	INNER JOIN Loc_Modelo M ON V.cd_modelo = M.cd_Modelo
	INNER JOIN Loc_Proprietario P ON V.cd_proprietario = P.cd_proprietario
	INNER Join Loc_cor c on v.cd_cor = c.cd_cor;

-- 2
SELECT Nr_Placa, Nm_Modelo, Nm_Proprietario, Vl_Diaria, desc_cor
	FROM Loc_Veiculo V
	INNER JOIN Loc_Modelo M ON V.cd_modelo = M.cd_Modelo
	INNER JOIN Loc_Proprietario P ON V.cd_proprietario = P.cd_proprietario
	INNER Join Loc_cor c on v.cd_cor = c.cd_cor
	WHERE Vl_Diaria < 1000;

-- 3
SELECT desc_Cor, avg(Vl_Diaria)
	FROM ex01
	GROUP BY desc_Cor;
 
-- 4 
Select Nm_proprietario, avg(Vl_diaria)
	from ex01
	group by Nm_proprietario;
    
-- 5
Select desc_cor, avg(vl_diaria)
	from ex01
    group by desc_cor
	having avg(vl_diaria) > (Select avg(Vl_diaria) from loc_veiculo);
	

-- 6 
SELECT Nr_Placa, Nm_Modelo, Nm_Proprietario, desc_cor, vl_diaria
	FROM Loc_Veiculo V
	INNER JOIN Loc_Modelo M ON V.cd_modelo = M.cd_Modelo
	INNER JOIN Loc_Proprietario P ON V.cd_proprietario = P.cd_proprietario
	INNER Join Loc_cor c on v.cd_cor = c.cd_cor
    where vl_diaria > (Select avg(Vl_diaria) from loc_veiculo);
 
 -- 7
 SELECT Nr_Placa, Nm_Modelo, Nm_Proprietario, desc_cor, Vl_diaria
	FROM Loc_Veiculo V
	INNER JOIN Loc_Modelo M ON V.cd_modelo = M.cd_Modelo
	INNER JOIN Loc_Proprietario P ON V.cd_proprietario = P.cd_proprietario
	INNER Join Loc_cor c on v.cd_cor = c.cd_cor
    WHERE vl_diaria > any (SELECT avg(Vl_Diaria)
							FROM ex01
							GROUP BY desc_Cor);
                
-- 8 
 SELECT Nr_Placa, Nm_Modelo, Nm_Proprietario, desc_cor, Vl_diaria
	FROM Loc_Veiculo V
	INNER JOIN Loc_Modelo M ON V.cd_modelo = M.cd_Modelo
	INNER JOIN Loc_Proprietario P ON V.cd_proprietario = P.cd_proprietario
	INNER Join Loc_cor c on v.cd_cor = c.cd_cor
    WHERE vl_diaria > all (SELECT avg(Vl_Diaria)
							FROM ex01
							GROUP BY desc_Cor);                            
-- 9 
 SELECT Nr_Placa, Nm_Modelo, Nm_Proprietario, desc_cor, Vl_diaria
	FROM Loc_Veiculo V
	INNER JOIN Loc_Modelo M ON V.cd_modelo = M.cd_Modelo
	INNER JOIN Loc_Proprietario P ON V.cd_proprietario = P.cd_proprietario
	INNER Join Loc_cor c on c.cd_cor = v.cd_cor
    WHERE vl_diaria > any(SELECT avg(Vl_Diaria)
							FROM ex01
							GROUP BY Nm_proprietario);
-- 10 
Create view ex01 as
	(SELECT Nr_Placa, Nm_Modelo, Nm_Proprietario, desc_cor, vl_diaria
	FROM Loc_Veiculo V
	INNER JOIN Loc_Modelo M ON V.cd_modelo = M.cd_Modelo
	INNER JOIN Loc_Proprietario P ON V.cd_proprietario = P.cd_proprietario
	INNER Join Loc_cor c on v.cd_cor = c.cd_cor);
