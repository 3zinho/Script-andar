local objeto = Instance.new("Part") -- Cria um novo objeto do tipo Part
objeto.Size = Vector3.new(1, 1, 1) -- Define o tamanho do objeto
objeto.Position = Vector3.new(0, 10, 0) -- Define a posição inicial do objeto
objeto.Anchored = true -- Ancla o objeto para que ele não caia
objeto.Parent = game.Workspace -- Adiciona o objeto ao Workspace

local destino = Vector3.new(0, 10, 50) -- Define a posição de destino
local tempoParaMover = 5 -- Tempo em segundos para mover até o destino

-- Função para mover o objeto
local function moverObjeto()
    local inicio = objeto.Position
    local delta = destino - inicio
    local passo = delta / (tempoParaMover * 60) -- Divide pelo número de frames por segundo

    for i = 1, tempoParaMover * 60 do
        objeto.Position = objeto.Position + passo
        wait(1/60) -- Espera um frame
    end

    objeto:Destroy() -- Remove o objeto após chegar ao destino
end

moverObjeto() -- Chama a função para mover o objeto
