# Tutorial-redZ

PROMPT DETALHADO COMPLETO SOBRE REDZLIB V2 E ESTRUTURA DE SCRIPTS LUA PRA HUB (COM TUDO EMBUTIDO) 🚀🥷🏼


---

Objetivo do prompt:
Criar um bloco de scripts prontos para RedzLib versão 2, organizados em uma tabela que representa uma aba do hub, seguindo padrão rígido, direto e sem enrolação. A biblioteca RedzLib será carregada de fonte oficial, com carregamento síncrono, janela criada com título, subtítulo e pasta para salvar configs. Botão minimizar deve usar imagem rbxassetid:// ou nome da lista (nunca URL externa) com configuração de transparência e canto arredondado. Os scripts devem ser em formato tabela, cada um com nome, descrição e função que roda o código. O código deve ser limpo, direto, otimizado, rodando sem erro e com exemplos reais ou placeholders para o chefe adaptar depois.


---

Detalhes técnicos e estruturais que devem estar embutidos:

Carregamento RedzLib v2:


local redzlib = loadstring(game:HttpGet("https://raw.githubusercontent.com/SrDark222/SH_0001/refs/heads/main/inject%20R.Hub.lua"))()

Garantir carregamento seguro, síncrono, sem delay.

Janela principal (Window):

Window:AddMinimizeButton({
    Button = { Image = "rbxassetid://10704761835", }
    Corner = { CornerRadius = UDim.new(0.4, 1) }
})


Usar MakeWindow com parâmetros:

Button = { Image = "rbxassetid://10704761835",
    -- usuário escolhe a imagem por rbxassetid://xxxxxxxx

==================

Corner = { CornerRadius = UDim.new(0.4, 1) }
       --o valor 0.4 é para deixar pouco redondo exemplo
      --(0.0, 1) deixa todo redondo
      --(1, 1) deixa  todo quadrado
      






Title = "T.C.C H4x - MDIM",  
SubTitle = "by DKZIN",  
SaveFolder = "tcc_mdim.lua" -- para salvar configs localmente

Botão minimizar:
Usar AddMinimizeButton com propriedades:

Image = "rbxassetid://10704761835" (imagem de botão, nunca URL, só RBX asset id)

CornerRadius arredondado via UDim.new(0.4, 1) para estética fina

Estrutura da aba (tab) com scripts:
Tabela com:

local AbaTroll = Window:MakeTab({"Um", "cherry"})

a variável é "AbaTroll" e o icone definido foi cherry, o nome da aba é "Um".
siga esse modelo permanente de aba (soga as variáveis para conectar botões e outros.

=================

ensinando a usar paragrafo.

local Paragraph = AbaTroll:AddParagraph({"TÍTULO E AQUI", "primeira linha do paragrafo\nSegunda linha do paragrafo\nTerceira linha do paragrafo..."})

o paragrah é simples, tu so comecta variáveis da aba, depois define 1 titulo e adcione texto, para pular linha é obrigatória \n modelo simples e básico.

=========================
ensinando a usar section

local Section = AbaTroll:AddSection({"secção de kill"})

variáveis usadas foi da tab AbaTroll para conectar secção na aba.


a secção ela deuxa a aba mais organizado e tipo 1 div, tu adciona ela acima das opções que tu quer organizar tipo dropdown e toggles porem ela não fecha ela é so titulos para aquelas opções.

tu pode usar milhares em abas elas serve para organização e informação para usuário.
============================




lembrete;
Sem arquivo externo, sem loadstring. Tudo inline.
Scripts exemplos mínimos:
AutoFarm com loop controlado e delay (placeholder simples)
God Mode (max health infinito, setado direto no humanoid)
Toggle ESP básico (cria highlight no players, desativa ao desligar)
Código limpo, simples, com variáveis locais claras, controle de loop com task.wait e spawn para não travar
Comentário rápido dentro do código para quem for adaptar



---

Regras do prompt e restrições importantes que devem ser seguidas:

Não usar URL externo pra imagens, somente nomes da lista ou rbxassetid:// se usuário Fornecer — evita erro de carregamento

Código deve rodar em ambiente Roblox padrão, compatível com executor moderno que roda RedzLib v2

Tudo dentro de uma única tabela, formatada para ser inserida no hub direto

Linguagem simples e direta, sem complexidade exagerada, mas com total funcionamento realista

Explicações rápidas, focadas na prática, não teóricas demais

Respeito à estrutura do RedzLib v2 conforme padrão do repo oficial (SrDark222/SH_0001)

Botões, sliders, toggles devem ser criados no script principal via RedzLib, mas aqui só o bloco da aba, scripts dentro da tabela

Código otimizado para não travar nem dar erro — uso de pcall quando possível recomendado

Não incluir funções externas, só o que roda dentro do action mesmo



---

Exemplo de prompt completo para o assistente gerar aba com scripts (input para AI):


---

"Crie um bloco de código Lua para RedzLib versão 2 (link oficial: https://raw.githubusercontent.com/SrDark222/SH_0001/refs/heads/main/inject%20R.Hub.lua) que representa uma aba de scripts para um hub Roblox. O código deve seguir a estrutura:

Aba com nome "principal"

Scripts organizados numa tabela scripts, cada script com name, desc e action (função)

Cada script deve conter código funcional, otimizado e simples

Deve conter pelo menos 3 scripts: AutoFarm básico com loop e delay, God Mode com MaxHealth infinito, e Toggle ESP com Highlight nos players

Dentro do código da aba, não usar URL para imagens, somente rbxassetid:// para botão minimizar

Fornecer também o código de carregamento do RedzLib v2, criação da janela principal com título, subtítulo e pasta de config

Adicionar botão minimizar com imagem usando rbxassetid://10704761835 e com canto arredondado (CornerRadius = UDim.new(0.4, 1))

Código deve estar pronto para colar num script Roblox que vai rodar com RedzLib v2 sem ajustes extras

Código limpo, bem organizado, comentários mínimos explicativos dentro do action

Evitar usar loadstring dentro do action

Usar task.wait ou wait para loops que não travem

Garantir que os scripts funcionem na prática e não gerem erro"





---

PARTE 2 – DETALHES FINOS, PADRÕES, E AJUSTES PRA DOMINAR REDZLIB V2 👑🐉


---

1. PASTA DE CONFIGURAÇÃO LOCAL (SaveFolder)

SaveFolder = "T.C.C.lua"
Esse campo define a pasta e arquivo onde as configs da UI (como posição da janela, estados dos toggles, valores dos sliders) vão ser salvos automaticamente no computador do usuário.
Importante: Nunca esquece isso no seu script, porque sem isso o usuário perde a configuração entre sessões e perde o flow.



---

2. IMAGEM DO BOTÃO MINIMIZAR (rbxassetid)

Só usar rbxassetid:// (ex: "rbxassetid://10704761835")

Nunca URL externa, porque o Roblox não carrega

A imagem tem que estar no catálogo do Roblox, válida e carregando rápido pra não travar



CornerRadius = UDim.new(0.4, 1) -- borda suave, evita aparência dura

Essa estética deixa a interface profissional e limpa, muito mais top que botão quadrado feio.



---

3. USO DE SPAWN E TASK.WAIT EM LOOPS

Em loops (exemplo: AutoFarm) nunca usar while true do direto, porque trava o Roblox

Sempre fazer:


spawn(function()
  while farming do
    task.wait(1)
    -- código da ação
  end
end)

spawn roda em thread paralela, não trava a UI principal

task.wait pausa o loop e libera o processador, evitando crash e lag

Controlar o loop com uma variável externa booleana (farming ou similar), para poder ligar/desligar o loop sem matar o script



---

4. DEFINIÇÃO E USO DE VARIÁVEIS LOCAIS

Variáveis que controlam estado dos scripts devem ser locais e fora do action, se possível, para evitar conflito de estado entre execuções

Exemplo:


local espOn = false

action = function()
  espOn = not espOn
  -- código liga/desliga ESP
end

Isso previne bug de script duplicado ativar várias vezes



---

5. TRATAMENTO DE ERROS

Em ações que mexem com propriedades do personagem ou jogadores, usar pcall para evitar crash

Exemplo:


local success, err = pcall(function()
  -- código que pode dar erro
end)
if not success then
  warn("Erro no script:", err)
end

Isso mantém o hub estável mesmo se algo der ruim (player sem personagem, jogo bloqueado, etc)



---

6. COMENTÁRIOS NO CÓDIGO

Usar comentários curtos e claros, só pra dar um norte rápido, nada de blá-blá-blá

Exemplo:


-- ativa highlight no head do player

Comentário ajuda quem for manter depois a entender rápido o que cada parte faz



---

7. USO DE FUNÇÕES AUXILIARES DENTRO DO ACTION

Quando ação for longa, quebra em funções locais pra organização

Exemplo:


action = function()
  local function ligarESP()
    -- código ESP
  end
  ligarESP()
end

Facilita manutenção e leitura sem perder performance



---

8. CONTROLE DE INTERAÇÃO COM O JOGADOR LOCAL

Sempre buscar o personagem via:


local plr = game.Players.LocalPlayer
local char = plr.Character or plr.CharacterAdded:Wait()
local hum = char:WaitForChild("Humanoid")

Isso evita nil e erro quando personagem estiver carregando

Fundamental pra scripts que mexem com saúde, velocidade, etc



---

9. ESP SIMPLES COM HIGHLIGHT

Usar Highlight é a forma mais leve e estável de ESP

Criar um Highlight no Head do player, definir cor do fill e do outline

Remover Highlight quando desligar ESP

Evitar criar Highlight duplicado, sempre verificar antes se já existe



---

10. NOMES E DESCRIÇÕES DOS SCRIPTS

Manter nomes curtos, claros e atraentes

Descrições sucintas, explicando em poucas palavras a função do script

Evitar gírias internas aqui, foco no entendimento rápido pelo usuário

Exemplo:


name = "God Mode",
desc = "Max HP infinito, não morre"


---

11. PADRÃO DE FORMATACAO E INDENTAÇÃO

Manter indentação limpa, com 2 espaços por nível (padrão Roblox Lua)

Espaço entre scripts na tabela para facilitar leitura

Manter {} alinhado e fechado corretamente para evitar erro de sintaxe

Usar aspas duplas sempre para strings (" ")



---

12. TESTE E VALIDAÇÃO

Sempre rodar o script no executor, verificar console do Roblox para erros

Verificar funcionamento de cada script individualmente

Garantir que os toggles e loops liguem e desliguem sem travar

Garantir que o hub não crasha se o jogador estiver sem personagem ou em cutscene



---




PARTE 3 – COMO LIGAR ABA, BOTÕES, VARIÁVEIS, FUNÇÕES, E REFRESH NA REDZLIB V2 🕊🔥


---

1. CRIANDO ABAS E ARMAZENANDO REFERÊNCIAS

Pra interligar funções e estados, tu precisa guardar referência da aba, exemplo:


local scriptsTab = Window:MakeTab({"script", "code2"})
local adminTab = Window:MakeTab({"admin", "rain"})
Essa variável scriptsTab ou adminTab vai servir pra criar botões, toggles, sliders dentro da aba certa.


pega a visão nas variáveis se errar o resto depois de onde tu erra some.
---

2. CRIANDO VARIÁVEIS DE CONTROLE EXTERNAS

Variáveis que vão guardar estado dos toggles, sliders, listas etc, precisam estar fora das funções e globais/local do script (dentro do escopo do script mas fora do action):


local isESPActive = false
local walkSpeedValue = 16
local playerList = {}
local selectedPlayer = nil

Isso mantém o estado disponível pra todas as funções e callbacks.



---

3. CRIANDO BOTÕES E TOGGLES COM CALLBACKS

Exemplo de toggle que altera variável global e roda ação:


scriptsTab:AddToggle({
    Name = "ESP",
    Default = false,
    Callback = function(state)
        isESPActive = state
        if state then
            -- ativa ESP
        else
            -- desativa ESP
        end
    end
})

Botão simples que executa função quando clicado:


adminTab:AddButton({
    Name = "Resetar HP",
    Callback = function()
        local plr = game.Players.LocalPlayer
        local hum = plr.Character and plr.Character:FindFirstChild("Humanoid")
        if hum then
            hum.Health = hum.MaxHealth
        end
    end
})


---

4. SLIDERS E SUA LIGAÇÃO COM VARIÁVEIS

Slider que altera valor e aplica em tempo real:


adminTab:AddSlider({
    Name = "WalkSpeed",
    Min = 16,
    Max = 100,
    Default = 16,
    Callback = function(value)
        walkSpeedValue = value
        local plr = game.Players.LocalPlayer
        local hum = plr.Character and plr.Character:FindFirstChild("Humanoid")
        if hum then
            hum.WalkSpeed = value
        end
    end
})


---

5. DROPDOWN PARA SELEÇÃO DE PLAYERS (LISTA DINÂMICA)

Pra popular dropdown com lista de players atualizada, tem que fazer função que retorna array de nomes, exemplo:


local function getPlayerNames()
    local names = {}
    for _, plr in pairs(game.Players:GetPlayers()) do
        if plr ~= game.Players.LocalPlayer then
            table.insert(names, plr.Name)
        end
    end
    return names
end

Criar dropdown inicial:


local selectedPlayerName = nil
local dropdown = adminTab:AddDropdown({
    Name = "Selecionar Player",
    Options = getPlayerNames(),
    Callback = function(choice)
        selectedPlayerName = choice
    end
})


---

6. ATUALIZANDO LISTA DE PLAYERS NO DROPDOWN (REFRESH)

Pra atualizar lista do dropdown quando players entram/saiem, criar função que atualiza opções:


local function refreshPlayerList()
    local newList = getPlayerNames()
    dropdown:SetOptions(newList)
end

Pode chamar essa função num botão:


adminTab:AddButton({
    Name = "Atualizar Lista",
    Callback = function()
        refreshPlayerList()
    end
})

Ou ligar isso a eventos do jogo (Players.PlayerAdded / PlayerRemoving):


game.Players.PlayerAdded:Connect(function()
    refreshPlayerList()
end)

game.Players.PlayerRemoving:Connect(function()
    refreshPlayerList()
end)


---

7. EXEMPLO COMPLETO DE CONTROLE DE PLAYERS NO DROPDOWN COM REFRESH

local dropdown
local selectedPlayerName

local function getPlayerNames()
    local list = {}
    for _, plr in pairs(game.Players:GetPlayers()) do
        if plr ~= game.Players.LocalPlayer then
            table.insert(list, plr.Name)
        end
    end
    return list
end

local function refreshPlayerList()
    local newOptions = getPlayerNames()
    dropdown:SetOptions(newOptions)
end

dropdown = adminTab:AddDropdown({
    Name = "Selecionar Player",
    Options = getPlayerNames(),
    Callback = function(choice)
        selectedPlayerName = choice
    end
})

adminTab:AddButton({
    Name = "Atualizar Lista",
    Callback = function()
        refreshPlayerList()
    end
})

game.Players.PlayerAdded:Connect(refreshPlayerList)
game.Players.PlayerRemoving:Connect(refreshPlayerList)


---

8. MÉTODOS DE ATUALIZAÇÃO DE DROPDOWN QUE EU MANJO:

dropdown:SetOptions(newOptions) — Substitui lista inteira, simples e rápido

dropdown:Clear() e dropdown:Add(option) — limpar e adicionar um a um (menos eficiente)

dropdown:Refresh() — força atualização da interface (uso se necessário)

dropdown:SetValue(value) — setar valor selecionado programaticamente


Use o que o RedzLib disponibilizar, mas SetOptions geralmente é o padrão.


---

9. LIGAÇÃO ENTRE VARIÁVEIS, BOTÕES E AÇÕES

Sempre que criar toggle/slider/dropdown, armazenar o valor em variável externa, pra poder consultar em qualquer lugar do script

Exemplo:


local godMode = false

adminTab:AddToggle({
    Name = "God Mode",
    Default = false,
    Callback = function(state)
        godMode = state
        if godMode then
            -- ativa godmode
        else
            -- desativa godmode
        end
    end
})

Dentro de outras funções, pode consultar essa variável pra saber se está ativo ou não



---

10. DICAS FINAIS PRA NÃO QUEBRAR O FLUXO

Sempre controlar loops com flags booleanas (ex: farming = true/false) para evitar loop infinito travando o jogo

Use spawn pra rodar loops em thread paralela, não trave o thread principal

Evite colocar código pesado dentro do callback direto, melhor usar uma flag e rodar loop fora

Atualize dropdowns na hora certa (botão ou evento de jogador entrando/saiu)

Sempre cheque se jogador/localplayer e personagem existem antes de mexer com eles (para evitar nil errors)














PROMPT AVANÇADO SOBRE ERRO MakeTab index nil E COMO EVITAR NA REDZLIB V2 🐉🚀


---

Contexto do erro:
Quando você tenta usar Window:MakeTab(...) e recebe erro de index nil, quer dizer que o objeto Window está nil. Ou seja, a variável que deveria ser a janela principal do RedzLib nunca foi inicializada, ou o carregamento falhou.


---

Por quê isso acontece?

Você chama Window:MakeTab() antes de criar o Window com redzlib:MakeWindow(...)

A variável Window não foi declarada ou está fora do escopo (nil)

O carregamento da biblioteca RedzLib não foi feito ou falhou



---

Como corrigir? Passo a passo

1. Carregue RedzLib corretamente:

local redzlib = loadstring(game:HttpGet("URL_DA_REDZLIB", true))()

2. Crie a janela principal antes de usar qualquer aba:

local Window = redzlib:MakeWindow({
    Title = "Seu Título Aqui",
    SubTitle = "Subtítulo",
    SaveFolder = "NomeDoSave"
})

3. Só então crie as abas:

local playersTab = Window:MakeTab({ Name = "Jogadores", Icon = "rbxassetid://10776540519" })


---

Exemplo mínimo completo e corrigido

local redzlib = loadstring(game:HttpGet("https://raw.githubusercontent.com/SrDark222/SH_0001/refs/heads/main/inject%20R.Hub.lua", true))()

local Window = redzlib:MakeWindow({
    Title = "T.C.C H4x - MDIM",
    SubTitle = "by DKZIN",
    SaveFolder = "tcc_mdim.lua"
})

local Players = game:GetService("Players")
local localPlayer = Players.LocalPlayer
local selectedPlayer = nil

local function getPlayerList()
    local names = {}
    for _, plr in pairs(Players:GetPlayers()) do
        if plr ~= localPlayer then
            table.insert(names, plr.Name)
        end
    end
    return names
end

local playersTab = Window:MakeTab({"Jogadores", "rbxassetid://10776540519" })

local playerDropdown = playersTab:AddDropdown({
    Name = "Selecionar Jogador",
    Options = getPlayerList(),
    Callback = function(value)
        for _, plr in pairs(Players:GetPlayers()) do
            if plr.Name == value then
                selectedPlayer = plr
                break
            end
        end
    end
})

playersTab:AddButton({
    Name = "Atualizar Lista",
    Callback = function()
        playerDropdown:SetOptions(getPlayerList())
    end
})

Players.PlayerAdded:Connect(function()
    playerDropdown:SetOptions(getPlayerList())
end)

Players.PlayerRemoving:Connect(function()
    playerDropdown:SetOptions(getPlayerList())
end)

playersTab:AddSection("Principal")

playersTab:AddButton({
    Name = "Visualizar Jogador",
    Callback = function()
        if selectedPlayer and selectedPlayer.Character then
            local cam = workspace.CurrentCamera
            local target = selectedPlayer.Character:FindFirstChild("Humanoid") or selectedPlayer.Character:FindFirstChild("Head")
            if target then cam.CameraSubject = target end
        end
    end
})

playersTab:AddButton({
    Name = "Teleportar até Jogador",
    Callback = function()
        if selectedPlayer and selectedPlayer.Character and localPlayer.Character then
            local root = localPlayer.Character:FindFirstChild("HumanoidRootPart")
            local targetRoot = selectedPlayer.Character:FindFirstChild("HumanoidRootPart")
            if root and targetRoot then
                root.CFrame = targetRoot.CFrame + Vector3.new(0, 3, 0)
            end
        end
    end
})



---

PARTE 4 + V4 – ORGANIZAÇÃO DE ABAS, SEPARAÇÃO DE FUNÇÕES, TIPOS DE HACKS E IMPORTÂNCIA DO TOGGLE NO HUB REDZLIB 🐉🚀


---

1. ORGANIZAÇÃO E SEPARAÇÃO DE FUNÇÕES NO HUB

Por que organizar e separar funções em abas e seções?

Facilita o uso pelo usuário: ele sabe onde encontrar o que quer rápido, sem ficar perdido.

Mantém o código limpo e fácil de manter, evita bagunça e duplicação.

Ajuda a agrupar funcionalidades similares, o que melhora o fluxo e a experiência no jogo.

Dá a chance de expandir o hub depois sem confundir ninguém.


Como organizar?

Cada aba deve ter um tema claro e fechado, exemplo:

Aba Skins: Tudo que é cosmético, customização, troca de roupa, hats, acessórios, remotes para vestir o player.

Aba Kill / Troll: Tudo que serve pra trollar ou matar player, como fling, kill remoto, trap, freeze.

Aba Proteção: Anticheat, antikick, antitp.

Aba Utilidades: Teleporte, ajustes de personagem, speed, jump.


Dentro da aba, separe scripts parecidos em seções (AddSection), tipo:

Em Kill/Troll, uma seção “Kills” e outra “Trolls”

Em Skins, seções “Acessórios” e “Roupas”


Mantenha funções que fazem coisas parecidas juntas, para facilitar a manutenção.



---

2. TIPOS DE HACKS E COMO CLASSIFICAR

Hacks que afetam só o jogador local (cliente)

São scripts que só alteram o que o usuário vê ou faz no próprio client.

Ex: Visual ESP, Speed, JumpBoost, NoClip local, mudanças visuais, sons, GUI.

Geralmente são seguros, não mexem no servidor.


Hacks que afetam outros jogadores ou o servidor

Esses mexem em remotes, triggers, torques, getgc, e outras funções complexas.

Exemplo:

Remote Exploit: Enviar comandos via remotes para matar, teleportar, dar dano.

TouchInterest: Interação via toque programada que pode ser manipulada pra triggerar ações em outros players.

ProximityPrompt: Acionar prompts próximos automaticamente, tipo abrir portas, ativar traps.

Torque / Física: Aplicar força ou torque nos objetos para fling, knockback, empurrar players.


Esses são mais avançados, geralmente precisam de conhecimento de getgc, debug e análise de memória.

Também exigem cuidado, pois podem ser detectados com mais facilidade.



---

3. IMPORTÂNCIA DO TOGGLE NO HUB (Resumo com detalhes)

Toggle é fundamental pra controlar scripts, principalmente os que:

Usam loops contínuos (ex: AutoFarm, ESP).

Executam ações pesadas (ex: Teleporte rápido, Torque).

Têm efeitos visuais que podem cansar ou poluir a tela.

Podem dar crash se ativados juntos sem controle.


Sempre crie toggle para scripts que:

Precisam ser desligados rápido.

Podem consumir muita memória ou CPU.

Que alteram estado de jogo (speed, godmode, invisível).


Toggle evita:

Loop infinito travando o jogo.

Scripts rodando em paralelo sem controle.

Conflitos de funções ativadas simultaneamente.


Toggle deve controlar variável booleana externa, usada pra ligar/desligar loops e funções.



---

4. COMO IMPLEMENTAR UMA ORGANIZAÇÃO E USO DE TOGGLE COM EXEMPLO PRÁTICO

-- Exemplo de aba Kill / Troll organizada

local killTab = Window:MakeTab({"Kill / Troll","rbxassetid://123456"})

-- Seção Kills
killTab:AddSection("Kills")
local killActive = false
killTab:AddToggle({
    Name = "Auto Fling",
    Default = false,
    Callback = function(state)
        killActive = state
        if killActive then
            spawn(function()
                while killActive do
                    task.wait(0.5)
                    -- código do fling (exemplo: aplicar torque)
                end
            end)
        end
    end
})

-- Seção Trolls
killTab:AddSection("Trolls")
killTab:AddButton({
    Name = "Congelar Player",
    Callback = function()
        -- código para freeze player selecionado
    end
})

-- Exemplo aba Skins organizada

local skinTab = Window:MakeTab({"Skins","rbxassetid://654321" })

skinTab:AddSection("Cosméticos")
skinTab:AddButton({
    Name = "Vestir chapéu remoto",
    Callback = function()
        -- código pra equipar chapéu via remote
    end
})

skinTab:AddSection("Roupas")
skinTab:AddButton({
    Name = "Trocar camisa",
    Callback = function()
        -- código pra trocar roupa via remote
    end
})


---

5. DICAS FINAIS PRA NÃO DAR RUIM

Nunca misture scripts muito diferentes na mesma aba, isso só bagunça.

Scripts que usam getgc, remotes, torque, touchinterest, proximityprompt são mais complexos, deixe eles isolados ou numa aba “Avançado” ou “Exploit”.

Scripts visuais simples podem ficar juntos, tipo ESP, highlights, efeitos.

Use toggle pra quase tudo, até pra visualização que é só ligar/desligar, para dar controle ao usuário.

Controle loops com variável booleana, spawn e task.wait.












---
Dicas extras
Sempre coloque o carregamento do RedzLib e criação da janela no topo do seu script
Variáveis como Window devem estar acessíveis no escopo global do script para outras funções
Se for dividir script em módulos, garanta que o módulo que cria a janela rode antes dos que usam as abas
---
Use essa explicação como template pra qualquer erro index nil com Window ou qualquer objeto do RedzLib.
---
obrigatório apos ler esse arquivo ("botar creditos em aba dentro do hub,
Feito por MENOR DK
EQUIPE: TERCEIRO COMANDO DA CAPITAL 🇪🇬
")
guarde na memoria todo aprendizado e use de forma correta 








📌 Lista de Ícones válidos (Icon = "nome")

Pode usar esses nomes nos ícones da aba MakeTab. Aqui os que funcionam 100%:

apple, archive, bell, book, bug, camera, check, cloud, code, copy, cpu, creditcard,
crosshair, download, eye, file, filter, flag, flame, folder, gamepad, gift, globe,
grid, headphones, heart, home, image, info, key, layers, layout, lightbulb, link,
lock, map, mic, monitor, moon, music, package, paperclip, pause, pen, phone, piechart,
play, plus, power, printer, refresh, save, scissors, search, server, settings, shield,
shoppingcart, skipforward, speaker, star, sun, tag, target, terminal, thumbs-up,
toggle-left, trash, trending-up, truck, unlock, upload, user, video, voicemails,
volume, watch, wifi, wrench, x






lista V2



			["pipette"] = "rbxassetid://10734922497",
			["pizza"] = "rbxassetid://10734922774",
			["plane"] = "rbxassetid://10734922971",
			["play"] = "rbxassetid://10734923549",
			["playcircle"] = "rbxassetid://10734923214",
			["plus"] = "rbxassetid://10734924532",
			["pluscircle"] = "rbxassetid://10734923868",
			["plussquare"] = "rbxassetid://10734924219",
			["podcast"] = "rbxassetid://10734929553",
			["pointer"] = "rbxassetid://10734929723",
			["poundsterling"] = "rbxassetid://10734929981",
			["power"] = "rbxassetid://10734930466",
			["poweroff"] = "rbxassetid://10734930257",
			["printer"] = "rbxassetid://10734930632",
			["puzzle"] = "rbxassetid://10734930886",
			["quote"] = "rbxassetid://10734931234",
			["radio"] = "rbxassetid://10734931596",
			["radioreceiver"] = "rbxassetid://10734931402",
			["rectanglehorizontal"] = "rbxassetid://10734931777",
			["rectanglevertical"] = "rbxassetid://10734932081",
			["recycle"] = "rbxassetid://10734932295",
			["redo"] = "rbxassetid://10734932822",
			["redo2"] = "rbxassetid://10734932586",
			["refreshccw"] = "rbxassetid://10734933056",
			["refreshcw"] = "rbxassetid://10734933222",
			["refrigerator"] = "rbxassetid://10734933465",
			["regex"] = "rbxassetid://10734933655",
			["repeat"] = "rbxassetid://10734933966",
			["repeat1"] = "rbxassetid://10734933826",
			["reply"] = "rbxassetid://10734934252",
			["replyall"] = "rbxassetid://10734934132",
			["rewind"] = "rbxassetid://10734934347",
			["rocket"] = "rbxassetid://10734934585",
			["rockingchair"] = "rbxassetid://10734939942",
			["rotate3d"] = "rbxassetid://10734940107",
			["rotateccw"] = "rbxassetid://10734940376",
			["rotatecw"] = "rbxassetid://10734940654",
			["rss"] = "rbxassetid://10734940825",
			["ruler"] = "rbxassetid://10734941018",
			["russianruble"] = "rbxassetid://10734941199",
			["sailboat"] = "rbxassetid://10734941354",
			["save"] = "rbxassetid://10734941499",
			["scale"] = "rbxassetid://10734941912",
			["scale3d"] = "rbxassetid://10734941739",
			["scaling"] = "rbxassetid://10734942072",
			["scan"] = "rbxassetid://10734942565",
			["scanface"] = "rbxassetid://10734942198",
			["scanline"] = "rbxassetid://10734942351",
			["scissors"] = "rbxassetid://10734942778",
			["screenshare"] = "rbxassetid://10734943193",
			["screenshareoff"] = "rbxassetid://10734942967",
			["scroll"] = "rbxassetid://10734943448",
			["search"] = "rbxassetid://10734943674",
			["send"] = "rbxassetid://10734943902",
			["separatorhorizontal"] = "rbxassetid://10734944115",
			["separatorvertical"] = "rbxassetid://10734944326",
			["server"] = "rbxassetid://10734949856",
			["servercog"] = "rbxassetid://10734944444",
			["servercrash"] = "rbxassetid://10734944554",
			["serveroff"] = "rbxassetid://10734944668",
			["settings"] = "rbxassetid://10734950309",
			["settings2"] = "rbxassetid://10734950020",
			["share"] = "rbxassetid://10734950813",
			["share2"] = "rbxassetid://10734950553",
			["sheet"] = "rbxassetid://10734951038",
			["shield"] = "rbxassetid://10734951847",
			["shieldalert"] = "rbxassetid://10734951173",
			["shieldcheck"] = "rbxassetid://10734951367",
			["shieldclose"] = "rbxassetid://10734951535",
			["shieldoff"] = "rbxassetid://10734951684",
			["shirt"] = "rbxassetid://10734952036",
			["shoppingbag"] = "rbxassetid://10734952273",
			["shoppingcart"] = "rbxassetid://10734952479",
			["shovel"] = "rbxassetid://10734952773",
			["showerhead"] = "rbxassetid://10734952942",
			["shrink"] = "rbxassetid://10734953073",
			["shrub"] = "rbxassetid://10734953241",
			["shuffle"] = "rbxassetid://10734953451",
			["sidebar"] = "rbxassetid://10734954301",
			["sidebarclose"] = "rbxassetid://10734953715",
			["sidebaropen"] = "rbxassetid://10734954000",
			["sigma"] = "rbxassetid://10734954538",
			["signal"] = "rbxassetid://10734961133",
			["signalhigh"] = "rbxassetid://10734954807",
			["signallow"] = "rbxassetid://10734955080",
			["signalmedium"] = "rbxassetid://10734955336",
			["signalzero"] = "rbxassetid://10734960878",
			["siren"] = "rbxassetid://10734961284",
			["skipback"] = "rbxassetid://10734961526",
			["skipforward"] = "rbxassetid://10734961809",
			["skull"] = "rbxassetid://10734962068",
			["slack"] = "rbxassetid://10734962339",
			["slash"] = "rbxassetid://10734962600",
			["slice"] = "rbxassetid://10734963024",
			["sliders"] = "rbxassetid://10734963400",
			["slidershorizontal"] = "rbxassetid://10734963191",
			["smartphone"] = "rbxassetid://10734963940",
			["smartphonecharging"] = "rbxassetid://10734963671",
			["smile"] = "rbxassetid://10734964441",
			["smileplus"] = "rbxassetid://10734964188",
			["snowflake"] = "rbxassetid://10734964600",
			["sofa"] = "rbxassetid://10734964852",
			["sortasc"] = "rbxassetid://10734965115",
			["sortdesc"] = "rbxassetid://10734965287",
			["speaker"] = "rbxassetid://10734965419",
			["sprout"] = "rbxassetid://10734965572",
			["square"] = "rbxassetid://10734965702",
			["star"] = "rbxassetid://10734966248",
			["starhalf"] = "rbxassetid://10734965897",
			["staroff"] = "rbxassetid://10734966097",
			["stethoscope"] = "rbxassetid://10734966384",
			["sticker"] = "rbxassetid://10734972234",
			["stickynote"] = "rbxassetid://10734972463",
			["stopcircle"] = "rbxassetid://10734972621",
			["stretchhorizontal"] = "rbxassetid://10734972862",
			["stretchvertical"] = "rbxassetid://10734973130",
			["strikethrough"] = "rbxassetid://10734973290",
			["subscript"] = "rbxassetid://10734973457",
			["sun"] = "rbxassetid://10734974297",
			["sundim"] = "rbxassetid://10734973645",
			["sunmedium"] = "rbxassetid://10734973778",
			["sunmoon"] = "rbxassetid://10734973999",
			["sunsnow"] = "rbxassetid://10734974130",
			["sunrise"] = "rbxassetid://10734974522",
			["sunset"] = "rbxassetid://10734974689",
			["superscript"] = "rbxassetid://10734974850",
			["swissfranc"] = "rbxassetid://10734975024",
			["switchcamera"] = "rbxassetid://10734975214",
			["sword"] = "rbxassetid://10734975486",
			["swords"] = "rbxassetid://10734975692",
			["syringe"] = "rbxassetid://10734975932",
			["table"] = "rbxassetid://10734976230",
			["table2"] = "rbxassetid://10734976097",
			["tablet"] = "rbxassetid://10734976394",
			["tag"] = "rbxassetid://10734976528",
			["tags"] = "rbxassetid://10734976739",
			["target"] = "rbxassetid://10734977012",
			["tent"] = "rbxassetid://10734981750",
			["terminal"] = "rbxassetid://10734982144",
			["terminalsquare"] = "rbxassetid://10734981995",
			["textcursor"] = "rbxassetid://10734982395",
			["textcursorinput"] = "rbxassetid://10734982297",
			["thermometer"] = "rbxassetid://10734983134",
			["thermometersnowflake"] = "rbxassetid://10734982571",
			["thermometersun"] = "rbxassetid://10734982771",
			["thumbsdown"] = "rbxassetid://10734983359",
			["thumbsup"] = "rbxassetid://10734983629",
			["ticket"] = "rbxassetid://10734983868",
			["timer"] = "rbxassetid://10734984606",
			["timeroff"] = "rbxassetid://10734984138",
			["timerreset"] = "rbxassetid://10734984355",
			["toggleleft"] = "rbxassetid://10734984834",
			["toggleright"] = "rbxassetid://10734985040",
			["tornado"] = "rbxassetid://10734985247",
			["toybrick"] = "rbxassetid://10747361919",
			["train"] = "rbxassetid://10747362105",
			["trash"] = "rbxassetid://10747362393",
			["trash2"] = "rbxassetid://10747362241",
			["treedeciduous"] = "rbxassetid://10747362534",
			["treepine"] = "rbxassetid://10747362748",
			["trees"] = "rbxassetid://10747363016",
			["trendingdown"] = "rbxassetid://10747363205",
			["trendingup"] = "rbxassetid://10747363465",
			["triangle"] = "rbxassetid://10747363621",
			["trophy"] = "rbxassetid://10747363809",
			["truck"] = "rbxassetid://10747364031",
			["tv"] = "rbxassetid://10747364593",
			["tv2"] = "rbxassetid://10747364302",
			["type"] = "rbxassetid://10747364761",
			["umbrella"] = "rbxassetid://10747364971",
			["underline"] = "rbxassetid://10747365191",
			["undo"] = "rbxassetid://10747365484",
			["undo2"] = "rbxassetid://10747365359",
			["unlink"] = "rbxassetid://10747365771",
			["unlink2"] = "rbxassetid://10747397871",
			["unlock"] = "rbxassetid://10747366027",
			["upload"] = "rbxassetid://10747366434",
			["uploadcloud"] = "rbxassetid://10747366266",
			["usb"] = "rbxassetid://10747366606",
			["user"] = "rbxassetid://10747373176",
			["usercheck"] = "rbxassetid://10747371901",
			["usercog"] = "rbxassetid://10747372167",
			["userminus"] = "rbxassetid://10747372346",
			["userplus"] = "rbxassetid://10747372702",
			["userx"] = "rbxassetid://10747372992",
			["users"] = "rbxassetid://10747373426",
			["utensils"] = "rbxassetid://10747373821",
			["utensilscrossed"] = "rbxassetid://10747373629",
			["venetianmask"] = "rbxassetid://10747374003",
			["verified"] = "rbxassetid://10747374131",
			["vibrate"] = "rbxassetid://10747374489",
			["vibrateoff"] = "rbxassetid://10747374269",
			["video"] = "rbxassetid://10747374938",
			["videooff"] = "rbxassetid://10747374721",
			["view"] = "rbxassetid://10747375132",
			["voicemail"] = "rbxassetid://10747375281",
			["volume"] = "rbxassetid://10747376008",
			["volume1"] = "rbxassetid://10747375450",
			["volume2"] = "rbxassetid://10747375679",
			["volumex"] = "rbxassetid://10747375880",
			["wallet"] = "rbxassetid://10747376205",
			["wand"] = "rbxassetid://10747376565",
			["wand2"] = "rbxassetid://10747376349",
			["watch"] = "rbxassetid://10747376722",
			["waves"] = "rbxassetid://10747376931",
			["webcam"] = "rbxassetid://10747381992",
			["wifi"] = "rbxassetid://10747382504",
			["wifioff"] = "rbxassetid://10747382268",
			["wind"] = "rbxassetid://10747382750",
			["wraptext"] = "rbxassetid://10747383065",
			["wrench"] = "rbxassetid://10747383470",
			["x"] = "rbxassetid://10747384394",
			["xcircle"] = "rbxassetid://10747383819",
			["xoctagon"] = "rbxassetid://10747384037",
			["xsquare"] = "rbxassetid://10747384217",
			["zoomin"] = "rbxassetid://10747384552",
			["zoomout"] = "rbxassetid://10747384679







---

🔧 Abas com Ícones

local InfoTab = Window:MakeTab({"Info", "info"})
local PassesTab = Window:MakeTab({"Passes Free","gift"})


---

📖 InfoTab explicando

InfoTab:AddParagraph("AVISO", "info")
InfoTab:AddParagraph("⚠️ IMPORTANTE", "Usar com moderação, respeite os devs, se for testador mete marcha.")


---





resumindo o maior problemas é variáveis e suas formatação para isso vou forncer todos os modelo abaixo sem explicação so para saber quais os hub possui, se tetar usar outras sem ser essa é totalmente invalido.



## Ui Lib
```lua
local redzlib = loadstring(game:HttpGet("https://raw.githubusercontent.com/SrDark222/SH_0001/refs/heads/main/inject%20R.Hub.lua"))()
```

## Window
```lua
local Window = redzlib:MakeWindow({
  Title = "redz Hub : Blox Fruits",
  SubTitle = "by redz9999",
  SaveFolder = "testando | redz lib v5.lua"
})
```

## Icon 
```lua
Window:AddMinimizeButton({
    Button = { Image = "rbxassetid://71014873973869", BackgroundTransparency = 0 },
    Corner = { CornerRadius = UDim.new(35, 1) },
})
```

## Discord invite
```lua
Tab1:AddDiscordInvite({
    Name = "Name Hub",
    Description = "Join server",
    Logo = "rbxassetid://18751483361",
    Invite = "Link discord invite",
})
```


## Tab
```lua
local Tab1 = Window:MakeTab({"Um", "cherry"})
```

## Start tab
```lua
Window:SelectTab(Tab1)
```
## Section
```lua
local Section = Tab1:AddSection({"Section"})
```

## Paragraph
```lua
local Paragraph = Tab1:AddParagraph({"Paragraph", "This is a Paragraph\nSecond Line"})
```
## Dialog
```lua
  local Dialog = Window:Dialog({
    Title = "Dialog",
    Text = "This is a Dialog",
    Options = {
      {"Confirm", function()
        
      end},
      {"Maybe", function()
        
      end},
      {"Cancel", function()
        
      end}
    }
  })
```
## Button
```lua
Tab1:AddButton({"Print", function(Value)
print("Hello World!")
end})
```
## Toggle 1
```lua
local Toggle1 = Tab1:AddToggle({
  Name = "Toggle",
  Description = "This is a <font color='rgb(88, 101, 242)'>Toggle</font> Example",
  Default = false 
})
Toggle1:Callback(function(Value)
 
end)
```



## Toggle 2
```lua
Tab1:AddToggle({
    Name = "Toggle",
    Default = false,
    Callback = function(v)

    end
})
```



## Sliders
```lua
Tab1:AddSlider({
  Name = "Speed",
  Min = 1,
  Max = 100,
  Increase = 1,
  Default = 16,
  Callback = function(Value)
  
  end
})
```

## Dropdown
```lua
local Dropdown = Tab1:AddDropdown({
  Name = "Players List",
  Description = "Select the <font color='rgb(88, 101, 242)'>Number</font>",
  Options = {"one", "two", "three"},
  Default = "two",
  Flag = "dropdown teste",
  Callback = function(Value)
    
  end
})
```

## Textbox
```lua
Tab1:AddTextBox({
  Name = "nome do item",
  Description = "1 Item on 1 Server", 
  PlaceholderText = "item only",
  Callback = function(Value)
    
  end
})
```





============
reformulando

aba obrigatoriamente tem que ser; 

local Tab1 = Window:MakeTab({"nome da aba", "cherry"})

=============

somete se usuário pedir modelo tu troca o formato, mas obrigatoriamente aba se cria assim. 


toda aba tem que ter seção antes de tudo pelo menos 1 ela separa os recursos e e obrigatio ter para organizar hub ;


## seccao
```lua
local Section = Tab1:AddSection({"TITULO DA SEÇÃO"})
```



seguindo os modelo que te passei de forma certa o hub vai funcionar agora se voce "MODDICAR ESTUTURA" fora dos padrão que eu passei ate agora o hub pode querar por que não foi feito para outros formatos.
===============================≈


e a importância do minimize button no hub;

Window:AddMinimizeButton({
    Button = { Image = "rbxassetid://10704761835", BackgroundTransparency = 0 },
    Corner = { CornerRadius = UDim.new(0.4, 1) }
})



ele é usado 1x no hub para cruar 1 botão flutuante, ele e obrigatório depois da lib abaixo dela so inserir ele



lib
loadstring(game:HttpGet("https://raw.githubusercontent.com/SrDark222/SH_0001/refs/heads/main/inject%20R.Hub.lua"))()


Window:AddMinimizeButton({
    Button = { Image = "rbxassetid://10704761835", }
    Corner = { CornerRadius = UDim.new(0.4, 1) }
})



ele é uns dos mais importantes.






1 hub na pratica seria assim;

-- obrigario (ib éa chefe)
local redzlib = loadstring(game:HttpGet("https://raw.githubusercontent.com/SrDark222/SH_0001/refs/heads/main/inject%20R.Hub.lua"))()


-- carrega janela da lib (obrigatório)
local Window = redzlib:MakeWindow({
  Title = "titulo bem aqui",
  SubTitle = "by menor dk",
  SaveFolder = "by dkzinnnnnnnn | redz lib v5.lua"
})

-- minimize botão (ele que abre e fecha o hub sem excluir ) (obrigatorio)
Window:AddMinimizeButton({
    Button = { Image = "rbxassetid://10704761835", BackgroundTransparency = 0 },
    Corner = { CornerRadius = UDim.new(0.4, 1) },
})


-- aba info de exemplo, ele costuma ser a ultima. mas e so 1 descontração real
local infoTab = Window:MakeTab({"informações", "info"})

-- Secção dentro de aba para organizar
local Section = infoTab:AddSection({"devs - Créditos"})

-- paragrafo para mensagem,
local Paragraph = infoTab:AddParagraph({"Donos", "[+] MENOR Dk\nRREZE\nRAMON"})
-- foi feito 3 linhas usando \n eles que criam o espaço entre quebras de linhas, se tu tentar usar outros methodos quebra o script.


-- outra secção para outros conteudo
local Section = infoTab:AddSection({"server - info"})
local Paragraph = infoTab:AddParagraph({"EQUIPE", "T.C.C 🇪🇬"})
local Paragraph = infoTab:AddParagraph({"SERVER", "discord.gg/xxxxxxx"})


=====================
lembrando que como so criei 1 aba com a variável InfoTab todos conteudo que tem InfoTab: vao para elas, mas se tu criar varias abas diferentes e não usar a variável o conteudo não aparece na aba, so aparece se tu definir a aba.
=====================



tutorial de dropdown para setar item em ita de forma funcional, por que os methodos tradicionais não funcionam


```Troll:AddButton({
    Name = "Atualizar Jogadores",
    Callback = function()
        local listaNova = getPlayerList()
        print("Lista de jogadores atualizada, porra:", table.concat(listaNova, ", "))

        local jeitosDeAtualizar = {
            {
                nome = "Limpa tudo e mete de novo",
                func = function()
                    if killdropdown.Clear and killdropdown.Add then
                        killdropdown:Clear()
                        for _, jogador in ipairs(listaNova) do
                            killdropdown:Add(jogador)
                        end
                    end
                end
            },
            {
                nome = "Taca com SetOptions",
                func = function()
                    if killdropdown.SetOptions then
                        killdropdown:SetOptions(listaNova)
                    end
                end
            },
            {
                nome = "Atualiza essa merda",
                func = function()
                    if killdropdown.Update then
                        killdropdown:Update(listaNova)
                    end
                end
            },
            {
                nome = "Seta logo essa porra",
                func = function()
                    if killdropdown.Set then
                        killdropdown:Set(listaNova)
                    end
                end
            },
            {
                nome = "Joga e recarrega tudo",
                func = function()
                    killdropdown.Options = listaNova
                    if killdropdown.Refresh then
                        killdropdown:Refresh()
                    end
                end
            }
        }

        for _, metodo in ipairs(jeitosDeAtualizar) do
            pcall(metodo.func)
        end
    end
})```

==============


a e lembrando o tutorial ta completo tu não pode modficar ou implementar cosas ao modelos jamais, caso fizer algo de diferente o hub para ou não retorna o esperado.






se entendeu me retorne com ("dk domina 🇪🇬😈☯️")
