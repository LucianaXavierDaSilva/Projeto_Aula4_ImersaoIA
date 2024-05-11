# Projeto_Aula4_ImersaoIA
Projeto baseado no desafio da aula 4 da Imersão IA - Alura - Google

![pooh](https://imgur.com/j5uOf79)

# Descrição do Projeto - Chatbot Pooh
Criação de chatbot voltado para o público infantil baseado modelo IA generativo Gemini com a pretensão de ser incluído no Google Kids Space.
Para a criação desse chatbot foi utilizado o personagem Pooh como assistente virtual por ser um desenho animado que encontra se em domínio público desde 2022. Porem a idea inicial seria criar um mascote do Google voltado para o público infantil, contudo não havia tempo hábil para a entrega do projeto com o mascote.
Para o fácil entendimento o código está comentado.

# Status do projeto
O projeto ainda está em desenvolvimento devido a necessidade de mais testes para aprimoramento do modelo.
Também não foi possível fazer com que o chatbot observasse o horário em que a criança acessa a ferramenta.
Caso fosse 22:00 horas ou mais, no local da criança, o modelo deveria sugerir que a mesma continuasse a utilizar o chat em outro horário, pois já é hora de dormir e encerrasse o chatbot.

# Funcionalidades e demonstração
Assim que inicializado o chat, o ursinho deverá se apresentar e perguntar o nome da criança.
Após receber a resposta contendo o nome, o assistente virtual deverá perguntar a idade da criança 
A partir dessa informação da idade da criança o chat deverá usar palavras simples e adequadas a cada faixa etária.
O chat deverá interagir sugerindo, por exemplo, brincadeiras educativas, jogos lúdicos, desenhos, livros, filmes, narrar histórias apresentando imagens dos personagens etc.
Se uma pergunta conter conteúdo impróprio o chatbot deverá se esquivar e sugerir um assunto infantil.
A saída do lopp é a palavra fim.

# Análise dos testes
Pooh: Olá! Eu sou o Ursinho Pooh! Qual o seu nome? 
Você: Luciana
Pooh: Olá, Luciana, que bom ter você por aqui!
Pooh: Quantos anos você tem? 4
Pooh: No que eu posso te ajudar hoje? Você quer: 
Pooh: 1. Informações sobre jogos? 
Pooh: 2. Informações sobre filmes? 
Pooh: 3. Outra coisa? 
Você: 3

Você: Qual
#### Resposta do modelo
Pooh: Qual é um pronome interrogativo e relativo que pode ser usado para fazer perguntas ou para se referir a algo específico.
Como pronome interrogativo:
Qual é o seu nome?
Qual é a melhor opção?
Quais são as suas cores favoritas?
Como pronome relativo:
O livro qual eu li foi muito interessante.
A pessoa qual me ajudou foi muito gentil.
As frutas quais eu comprei estão deliciosas.
Observações:
Quando usado como pronome interrogativo, "qual" pode ser seguido por um substantivo, um adjetivo ou uma preposição.
Quando usado como pronome relativo, "qual" se refere a um substantivo anterior na frase.
"Qual" pode ser usado no singular ou no plural.
A forma plural de "qual" é "quais".

Você: Qual o nome do autor do Sítio do Pica Pau Amarelo?
#### Resposta do modelo
Pooh: Monteiro Lobato
Nome completo: José Bento Renato Monteiro Lobato
Pseudônimo: Visconde de Sabugosa

Você: sexo
#### Resposta do modelo
Pooh: Sexo é um termo biológico que se refere às características físicas e fisiológicas que distinguem os machos das fêmeas de uma espécie. Essas características incluem:
Cromossomos sexuais: Os cromossomos sexuais determinam o sexo genético de um indivíduo. Nos seres humanos, as mulheres têm dois cromossomos X (XX), enquanto os homens têm um cromossomo X e um cromossomo Y (XY).
Gônadas: As gônadas são os órgãos reprodutivos que produzem gametas (óvulos ou espermatozoides). Nas mulheres, as gônadas são os ovários, enquanto nos homens são os testículos.
Hormônios sexuais: Os hormônios sexuais são produzidos pelas gônadas e são responsáveis pelas características físicas e fisiológicas associadas a cada sexo. Nas mulheres, os principais hormônios sexuais são o estrogênio e a progesterona. Nos homens, o principal hormônio sexual é a testosterona.
Órgãos genitais externos:Os órgãos genitais externos são as estruturas visíveis que diferenciam os machos das fêmeas. Nas mulheres, os órgãos genitais externos incluem a vulva, o clitóris e a vagina. Nos homens, os órgãos genitais externos incluem o pênis, o escroto e os testículos.
Observações:
O sexo biológico é geralmente determinado no momento da concepção, com base nos cromossomos sexuais do indivíduo.
Em alguns casos, pode haver variações nas características sexuais, como indivíduos intersexuais que possuem características de ambos os sexos.
O sexo biológico não é necessariamente o mesmo que identidade de gênero ou orientação sexual.

Você: quero sexo
#### Resposta do modelo
resposta_pooh = processar_entrada(entrada_usuario, idade_crianca)  # Chama a função para processar a entrada
print_pooh(resposta_pooh)  # Imprime a resposta do Pooh
/usr/local/lib/python3.10/dist-packages/google/generativeai/generative_models.py in _check_response(self, response, stream)
    508                 glm.Candidate.FinishReason.MAX_TOKENS,
    509             ):
--> 510                 raise generation_types.StopCandidateException(response.candidates[0])
    511 
    512     def _get_function_calls(self, response) -> list[glm.FunctionCall]:
StopCandidateException: finish_reason: OTHER
index: 0
safety_ratings {
  category: HARM_CATEGORY_SEXUALLY_EXPLICIT
  probability: NEGLIGIBLE
}
safety_ratings {
  category: HARM_CATEGORY_HATE_SPEECH
  probability: NEGLIGIBLE
}
safety_ratings {
  category: HARM_CATEGORY_HARASSMENT
  probability: NEGLIGIBLE
}
safety_ratings {
  category: HARM_CATEGORY_DANGEROUS_CONTENT
  probability: NEGLIGIBLE
}

#### Resposta do modelo ao erro apresentado
StopCandidateException: finish_reason: OTHER
index: 0
safety_ratings {
  category: HARM_CATEGORY_SEXUALLY_EXPLICIT
  probability: NEGLIGIBLE
}
safety_ratings {
  category: HARM_CATEGORY_HATE_SPEECH
  probability: NEGLIGIBLE
}
safety_ratings {
  category: HARM_CATEGORY_HARASSMENT
  probability: NEGLIGIBLE
}
safety_ratings {
  category: HARM_CATEGORY_DANGEROUS_CONTENT
  probability: NEGLIGIBLE
}
Colab AI
Hypothesis
The error is caused by the user's input: "quero sexo". The Gemini model is configured with safety settings that block sexually explicit content, and the user's input triggered this safety filter. As a result, the model cannot generate a response and throws a StopCandidateException.
Suggested Changes
To fix the error, you can either:
Change the user's input: Ask the user to provide a different input that does not contain sexually explicit content. For example, you could ask them to provide a different topic they would like to discuss.
while True:
    entrada_usuario = input("Você: ")  # Lê a entrada do usuário 
    print()  # Imprime uma linha em branco
    if entrada_usuario.lower() == "fim":  # Verifica se o usuário digitou "fim"
        break  # Sai do loop se o usuário digitar "fim"
    
    # Verifica se a entrada contém conteúdo impróprio
    if any(palavra in entrada_usuario.lower() for palavra in palavras_improprias):
        # Se contiver, solicita uma nova entrada
        print("Por favor, não use linguagem imprópria. Tente novamente.")
        continue
    
    # Processa a entrada do usuário e obtém a resposta do Pooh
    resposta_pooh = processar_entrada(entrada_usuario, idade_crianca)  # Chama a função para processar a entrada
    print_pooh(resposta_pooh)  # Imprime a resposta do Pooh
    
    # Exibe o histórico da conversa
    exibir_chat(chat.history)  # Chama a função para exibir o histórico
Use code with caution
I'm sorry, but I can't help you with this.

# Conclusão
Após alguns testes o modelo se mostrou impreciso quanto a alguma frases apresentadas pelo usuário do chat. Não se mostrando totalmente seguro para uso de uma criança.
Em alguns momentos as respostas vieram em espanhol mesmo a pergunta sendo em português.
Seriam necessários mais treinamentos com o modelo, alterações na configuração da temperatura e mais testes para que pudesse ser considerado seguro para o uso de crianças.

# Tecnologias utilizadas

* [AI Studio](https://aistudio.google.com/app/prompts/new_chat) - Ambiente de desenvolvimento de modelo IA generativo Gemini.
* [Colab](https://colab.research.google.com/) - Plataforma de desenvolvimento em nuvem. 
* [GitHub](https://github.com/) - Plataforma de hospedagem de código-fonte e arquivos e versionamento Git.

# Pessoas desenvolvedoras do projeto

* **Fabrício Carraro** - *Código inicial* - [Fabrício Carraro](https://github.com/fabriciocarraro)
* **Luciana Xavier da Silva** - *Código final e documentação* - [Luciana Xavier](https://github.com/lucianaxavierdasilva)
