use carloca; 

-- 1 
SELECT Nr_Placa, Desc_Cor
	FROM Loc_Veiculo
	INNER JOIN Loc_Cor ON Loc_Veiculo.cd_cor = Loc_Cor.cd_Cor;
    
-- 2
SELECT Nm_Func, Vl_Salario, Cd_Depto
	FROM Loc_Funcionario
	WHERE Vl_Salario < 7000 AND Cd_Depto != 10;

-- 3
SELECT Nr_Placa, Vl_Diaria, Desc_Cor
	FROM Loc_Veiculo v
	INNER JOIN Loc_Cor c ON v.cd_cor = c.cd_Cor
	WHERE v.Vl_Diaria < 920;

-- 4
SELECT Nr_Placa, Nm_Proprietario, Nm_Modelo 
	FROM Loc_Veiculo v
	INNER JOIN Loc_Proprietario p ON v.Cd_Proprietario = p.cd_proprietario
	INNER JOIN Loc_Modelo m ON v.cd_Modelo = m.cd_Modelo
	WHERE p.cd_proprietario <= 5 AND m.cd_Modelo <= 5;
    
-- 5
SELECT v.Nr_Placa, p.Nm_Proprietario, Tp_Automovel
	FROM Loc_Veiculo v
	INNER JOIN Loc_Proprietario p ON v.Cd_Proprietario = p.cd_proprietario
	INNER JOIN Loc_Tp_Automovel t ON v.Tp_Automovel = Tp_Automovel
	WHERE p.cd_proprietario > 3 AND Tp_Automovel = 1;

-- 6
SELECT Nm_Func, Nm_Depto, Nm_Cargo
	FROM Loc_Funcionario f
	INNER JOIN Loc_Depto d ON f.Cd_Depto = d.Cd_Depto
	INNER JOIN Loc_Cargo c ON f.Cd_Cargo = c.Cd_Cargo
	WHERE f.Nm_Func like '%ri%';
    
-- 7
SELECT Nr_Pedido, Nm_Func
	FROM Loc_Pedido_Locacao pl
	INNER JOIN Loc_Funcionario f ON pl.Cd_Func = f.Cd_Func
	WHERE f.Vl_Salario < 5500;
    
-- 8
SELECT pl.Nr_Pedido, lc.Nm_Cliente, il.Nr_Placa
	FROM Loc_Pedido_Locacao pl
	INNER JOIN Loc_Item_Locacao il ON pl.Nr_Pedido = il.Nr_Pedido
	INNER JOIN Loc_Cliente lc ON pl.Cd_Cliente = lc.Cd_cliente
	WHERE pl.nr_pedido <= 100;
    
    -- 9
SELECT pl.Nr_Pedido, f.Nm_Func, v.Nr_Placa, v.Km_Atual
	FROM Loc_Pedido_Locacao pl
	INNER JOIN Loc_Item_Locacao il ON pl.Nr_Pedido = il.Nr_Pedido
	INNER JOIN Loc_Veiculo v ON il.Nr_Placa = v.Nr_Placa
	INNER JOIN Loc_Funcionario f ON pl.Cd_Func = f.Cd_Func;
    
    -- 10
SELECT pl.Nr_Pedido, f.Nm_Func, lv.Nr_Placa, v.Km_Atual
	FROM Loc_Pedido_Locacao pl
	INNER JOIN Loc_Item_Locacao i ON pl.Nr_Pedido = i.Nr_Pedido
	INNER JOIN Loc_Veiculo lv ON i.Nr_Placa = lv.Nr_Placa
	INNER JOIN Loc_Funcionario f ON pl.Cd_Func = f.Cd_Func
	JOIN Loc_Veiculo v ON i.Nr_Placa = v.Nr_Placa
	WHERE lv.vl_Diaria > 10000;
