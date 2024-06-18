use carloca;

-- 1
SELECT Nm_Fabricante, Nm_Modelo
	FROM Loc_Modelo m
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	ORDER BY f.Nm_Fabricante, m.Nm_Modelo;

-- 2
SELECT Nr_Placa, Vl_Diaria, Nm_Fabricante, Nm_Modelo
	FROM Loc_Veiculo v
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	WHERE v.Vl_Diaria > 200
	ORDER BY f.Nm_Fabricante,m.Nm_Modelo;

-- 3
SELECT Nm_Fabricante, SUM(v.Vl_Diaria)
	FROM Loc_Veiculo v
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	GROUP BY f.Nm_Fabricante;

-- 4
SELECT Nm_Fabricante, SUM(v.Vl_Diaria) 
	FROM Loc_Veiculo v
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	GROUP BY f.Nm_Fabricante
	HAVING SUM(v.Vl_Diaria) > 2000;

-- 5
SELECT Nm_Fabricante, SUM(v.Vl_Diaria) 
	FROM Loc_Veiculo v
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	WHERE v.Vl_Diaria > 200
	GROUP BY f.Nm_Fabricante
	HAVING SUM(v.Vl_Diaria) > 2000; 

-- 6 
SELECT Nr_Placa, Vl_Diaria, Nm_Fabricante, Nm_Modelo
	FROM Loc_Veiculo v
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	WHERE f.Nm_Fabricante = 'Fiat';
    
-- 7
SELECT MAX(v.Vl_Diaria) 
	FROM Loc_Veiculo v
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	WHERE f.Nm_Fabricante = 'Fiat';

-- 8
SELECT Nm_Modelo, Vl_Diaria
	FROM Loc_Veiculo v
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	WHERE v.Vl_Diaria > (SELECT MAX(lv.Vl_Diaria) FROM Loc_Veiculo lv INNER JOIN Loc_Modelo lm ON lv.cd_Modelo = lm.cd_Modelo 
						 INNER JOIN Loc_Fabricante lf ON lm.cd_Fabricante = lf.cd_Fabricante WHERE lf.Nm_Fabricante = 'Fiat');
    
-- 9
SELECT Nm_Modelo, Vl_Diaria
	FROM Loc_Veiculo v
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	WHERE v.Vl_Diaria > ( SELECT MAX(lv.Vl_Diaria) FROM Loc_Veiculo lv INNER JOIN Loc_Modelo lm ON lv.cd_Modelo = lm.cd_Modelo
					  INNER JOIN Loc_Fabricante lf ON lm.cd_Fabricante = lf.cd_Fabricante);
    
-- 10
SELECT Nm_Modelo
	FROM Loc_Veiculo v
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	INNER JOIN Loc_Fabricante f ON m.cd_Fabricante = f.cd_Fabricante
	WHERE f.Nm_Fabricante = 'Fiat'AND v.Vl_Diaria = (SELECT MAX(lv.Vl_Diaria) FROM Loc_Veiculo lv INNER JOIN Loc_Modelo lm ON lv.cd_Modelo = lm.cd_Modelo
													 INNER JOIN Loc_Fabricante lf ON lm.cd_Fabricante = lf.cd_Fabricante WHERE lf.Nm_Fabricante = 'Fiat');
