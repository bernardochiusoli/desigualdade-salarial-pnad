# desigualdade-salarial-pnad

# Como fatores de Sexo e raça influenciam a renda salarial media no Brasil e impactam nos recortes de grupos sub-representados.
TCC da Turma Fly 2026 - diversiData

`Python` `pandas` `scikit-learn` `[base usada]`

## O problema
Análise de como sexo e raça influenciam a renda salarial média no Brasil, evidenciando desigualdades e a sub-representação de grupos no mercado de trabalho.Investigamos como sexo e raça influenciam a renda salarial média no Brasil.
Analisamos as diferenças de remuneração entre grupos sociais.
O estudo é importante para evidenciar desigualdades e a sub-representação no mercado de trabalho

## Por que "sexo" e não "gênero"
A ideia original do grupo era ir além do recorte binário e investigar como a renda varia entre toda a comunidade LGBTQIAPN+ — não só entre homens e mulheres cisgênero, mas incluindo pessoas trans, não-binárias, travestis e outras identidades de gênero e orientações sexuais. Era, na essência, uma crítica social: mostrar a desigualdade que o "sexo binário" oficial esconde. Isso não foi possível: a PNAD Contínua — nossa única fonte de dados — não coleta informação de identidade de gênero ou orientação sexual em nenhuma de suas edições, apenas a variável "sexo" (homem/mulher, atribuído). Por isso, ao longo do projeto, ajustamos a linguagem de "gênero" para "sexo" em todo o material: é a variável que os dados oficiais brasileiros efetivamente permitem medir hoje, e a ausência da comunidade LGBTQIAPN+ dessa estatística é, ela mesma, parte do problema que queríamos apontar.

## Os dados
- Fonte: [[Rendimento médio mensal (R$) do trabalho principal segundo posição da ocupação com contribuição para a Previdência Social por sexo e raça/cor, Fonte:  (PNAD) e da Pesquisa Nacional por Amostra de Domicílios Contínua (PNAD Contínua) do IBGE, recorte, período 2022].]
- Recorte: [2022, Brasil, Apenas trabalhadores formais]
- Amostra neste repositorio: [ O arquivo de testes contém **[X] linhas**, disponibilizado exclusivamente para garantir a execução e testagem do código.]
- Como reproduzir: [ver dados/FONTE.md]

## O metodo
1. **Limpeza:** Exclusão dos registros sem renda salarial declarada (VD4020 nulo ou zero) e restrição a pessoas de 16 anos ou mais;.
2. **Variáveis:** sexo (V2007), raça/cor (V2010), idade (V2009), escolaridade (VD3004) e UF — códigos do IBGE traduzidos para texto.
3. **Modelo:**imputação pela mediana e padronização das numéricas (idade eescolaridade) e One-Hot nas categóricas, tudo dentro de um Pipeline doscikit-learn, Regressão Linear Múltipla].
4. **Justificativa:** Escolha feita por permitir isolar o impacto de cada característica demográfica no rendimento e medir a desigualdade salarial.

## Os resultados
- **[numero principal]** - É a diferença média salarial observada entre homens brancos e mulheres negras na mesma posição
- Trabalhadores sem contribuição para a previdência ganham, em média, X% menos
- O recorte de raça/cor apresentou maior peso na disparidade de renda do que o recorte de gênero nesta região

## O prototipo
[[Link do GitHub Pages][(https://github.com/bernardochiusoli/desigualdade-salarial-pnad)] - 

Este simulador interativo expõe o viés salarial do mercado ao demonstrar visualmente como sexo e raça alteram drasticamente a renda prevista pela PNAD Contínua para perfis profissionais idênticos.

## Limitacoes
⚠️ 1. Limitações do Modelo Estatístico (Isolamento de Variáveis)Efeito "Ceteris Paribus" Artificial: Na realidade, sexo e raça moldam as oportunidades de vida desde a infância. Ao travar idade e escolaridade, o modelo assume que uma mulher negra e um homem branco chegam ao mercado com as mesmas trajetórias, o que ignora o racismo e o machismo estruturais prévios ao emprego.Variáveis Omitidas: A PNAD não captura dados cruciais que impactam a renda, como produtividade individual, soft skills, redes de contatos (networking) e o prestígio da instituição onde a pessoa estudou.

📊 2. Limitações da Base de Dados (PNAD Contínua)Informalidade e Subdeclaração: Trabalhadores informais ou autônomos tendem a flutuar ou subdeclarar seus rendimentos na pesquisa, reduzindo a precisão do modelo para esses grupos.Super-ricos Subrepresentados: A PNAD é uma pesquisa domiciliar por amostragem e costuma não capturar os rendimentos do topo da pirâmide financeira (o 1% mais rico), onde a disparidade de sexo e raça pode ser ainda mais extrema.Falta de Dados Setoriais Específicos: A pesquisa traz grandes recortes (ex: "Indústria", "Comércio"), mas não diferencia se a pessoa é desenvolvedora de software ou assistente de TI, o que distorce a previsão para profissões de nicho.

💡 3. Limitações de Interpretação (Viés vs. Discriminação)Correlação não é Causalidade: O modelo aponta que o sexo e a raça estão associados a uma renda menor, mas ele não consegue explicar o motivo exato (se é discriminação direta do chefe, penalidade pela maternidade, ou barreiras de entrada em setores que pagam mais).Segregação Ocupacional Oculta: O modelo pode sugerir um viés puro na canetada do salário, quando na verdade parte da diferença ocorre porque mulheres e pessoas negras são empurradas para profissões historicamente menos valorizadas e pior pagas.

## O grupo

Ana Bezerra - [LinkedIn](https://www.linkedin.com/in/ana-almeida-ti/)

Jaqueline Martins Duarte - [LinkedIn](https://www.linkedin.com/in/jaquilenemartins)

Bernardo Chiusoli - [LinkedIn](https://www.linkedin.com/in/bernardochiusoli)

Victoria Paixão -[ LinkedIn](https://www.linkedin.com/in/victoria-aparecida)

Lorena - [LinkedIn](https://www.linkedin.com/in/lorena-g-a67978124)

Roberta - [LinkedIn](https://www.linkedin.com/in/roberta-bueno-de-souza-algarves-8226b8173)

Marina - [LinkedIn](https://www.linkedin.com/in/marina-sims-0a73a5196?utm_source=share_via&utm_content=profile&utm_medium=member_android)


## Como rodar
1. Abra `notebook/01_analise_completa.ipynb` no Google Colab
2. Rode as celulas de cima para baixo
3. As bibliotecas estao em `requisitos.txt`
