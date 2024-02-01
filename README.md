# :computer: [Desafio Técnico - Brudam](#computer-desafio-técnico---brudam-computer) :computer:

![Brudam](https://github.com/brudam-dev/brudam-test/blob/main/src/img/channels4_banner_dev.jpg) 

Olá! Seja bem-vindo ao desafio técnico da Brudam :)
 
Você já teve a chance de explorar o universo dinâmico do TMS? Sabia que, no cenário logístico global, o Brasil destaca-se como um dos países mais desafiadores devido à complexidade fiscal e legislativa? Desde 2004, a Brudam tem sido uma referência ao oferecer uma variedade de soluções especializadas para o setor logístico. Nos últimos anos, expandimos nossa presença para além das fronteiras nacionais.

Através de um sistema SaaS dedicado a transportadoras, o TMS Brudam aborda eficientemente questões operacionais no transporte de carga, desafios financeiros, integrações tecnológicas, soluções inovadoras em aplicativos e uma série de outras abordagens estratégicas. Estamos comprometidos em simplificar o cenário logístico e oferecer soluções adaptadas às demandas do mercado nacional e global. Se interessou? quer fazer parte do nosso time de tecnologia e fazer a diferença no mercado de transporte de cargas?

Leia com atenção todos os requisitos necessários para a entrega do desafio técnico e boa sorte!

## [:point_right: Sumário](#point_right-sumário)

- [:computer: Desafio Técnico - Brudam :computer:](#computer-desafio-técnico---brudam-computer)
  - [:point\_right: Sumário](#point_right-sumário)
  - [:rotating\_light: Avisos antes de iniciar](#rotating_light-avisos-antes-de-iniciar)
  - [:raised\_hands: O que deve ser enviado ao recrutador ao final do desafio?](#raised_hands-o-que-deve-ser-enviado-ao-recrutador-ao-final-do-desafio)
  - [:busts\_in\_silhouette: Instruções para o dia da entrevista técnica](#busts_in_silhouette-instruções-para-o-dia-da-entrevista-técnica)
  - [:books: Sobre o desafio técnico](#books-sobre-o-desafio-técnico)
    - [:arrow\_right: Cenário](#arrow_right-cenário)
    - [:arrow\_right: Endpoints](#arrow_right-endpoints)
    - [:arrow\_right: Payload](#arrow_right-payload)
    - [:arrow\_right: O que precisa ser feito?](#arrow_right-o-que-precisa-ser-feito)
    - [:arrow\_right: Observação sobre o teste](#arrow_right-observação-sobre-o-teste)
  - [:dart: Consideramos um diferencial](#dart-consideramos-um-diferencial)
  - [:heart: O que será avaliado](#heart-o-que-será-avaliado)
  - [:smile: Autores](#smile-autores)

## [:rotating_light: Avisos antes de iniciar](#rotating_light-avisos-antes-de-iniciar)
- Caso tenha chegado a este repositório sem ter sido contatado por um recrutador, por favor, antes de prosseguir com o desafio, faça o seu cadastro através deste link [FAÇA PARTE DO NOSSO TIME](https://quarkrh.com.br/brudam-servicos-de-tecnologia-da-informacao-ltda/vagas)
- Crie um repositório no seu GitHub, mas **não faça qualquer menção à Brudam**.
- Fique à vontade para consultar o **Google** ou **Stack Overflow** durante o desafio.
- Ao documentar suas instruções, seja claro e objetivo para facilitar o entendimento por parte de quem for revisar seu trabalho.
- Não hesite em tentar resolver os problemas propostos. Às vezes, é difícil determinar se você é capaz ou não, então, na dúvida, experimente!
- Não tenha receio de questionar os recrutadores se surgirem dúvidas durante o processo.
- Antes de enviar seu desafio, é altamente recomendável fazer uma avaliação minuciosa para garantir a qualidade do seu trabalho.
- Caso encontre alguma inconsistência por favor, informe aos seu recrutador.

## [:raised_hands: O que deve ser enviado ao recrutador ao final do desafio?](#raised_hands-o-que-deve-ser-enviado-ao-recrutador-ao-final-do-desafio)
> Nome completo
>
> Link do repositório
>
> Link do Linkedin

## [:busts_in_silhouette: Instruções para o dia da entrevista técnica](#busts_in_silhouette-instruções-para-o-dia-da-entrevista-técnica)
Na data estipulada pelo recrutador, assegure-se de ter sua aplicação em execução em sua máquina local para a realização dos testes e para nos apresentar os pontos desenvolvidos, bem como possíveis questionamentos. Durante o processo, faremos uma revisão de código contigo, como se você já fizesse parte do nosso time. Você terá a oportunidade de explicar sua abordagem, a arquitetura adotada e discutir possíveis melhorias para o projeto.

## [:books: Sobre o desafio técnico](#books-sobre-o-desafio-técnico)
### [:arrow_right: Cenário](#arrow_right-cenário) 
Como parte da equipe de desenvolvimento da Brudam, você foi designado para liderar a implementação de uma tela de rastreamento de entregas. A diretoria está ansiosa para oferecer aos clientes uma experiência mais transparente e detalhada sobre o status de suas cargas em trânsito. Para isso, foi disponibilizado dois endpoints para que você possa consumir essas informações.

### [:arrow_right: Endpoints](#arrow_right-endpoints) 

> [LINK PARA API_LISTAGEM_TRANSPORTADORAS](https://run.mocky.io/v3/e8032a9d-7c4b-4044-9d00-57733a2e2637)
> 
> [LINK PARA API_LISTAGEM_ENTREGAS](https://run.mocky.io/v3/6334edd3-ad56-427b-8f71-a3a395c5a0c7)
>
> Se você enfrentar problemas para acessar o link da API, você pode baixar os exemplos .json correspondentes a partir deste repositório para utilização. São estes arquivos:
> 
> API_LISTAGEM_TRANSPORTADORAS.json
> 
> API_LISTAGEM_ENTREGAS.json.json

### [:arrow_right: Payload](#arrow_right-payload) 

```
// API_LISTAGEM_TRANSPORTADORAS

{
   "_id":"1f0a1c69...",   // UUID chave primária da transportadora
   "_cnpj":1234567...,    // CNPJ da transportadora
   "_fantasia":"SWIFT..." // Fantasia da transportadora
}
```

```
// API_LISTAGEM_ENTREGAS

{
   "_id":"f1e7be5c...",                // UUID chave primária da entrega
   "_id_transportadora":"1f0a1c69...", // UUID chave estrangeira da transportadora 
   "_volumes":1,                       // Total de volumes a serem entregues
   "_remetente":{
      // Informações sobre o remetente.
      ...
   },
   "_destinatario":{
      // Informações sobre o destinatário.
      ...
      "_geolocalizao":{
         // Geolocalização fictícia do destinatário.
         ...
      }
   },
   "_rastreamento":[
     // Histórico de todas as ocorrências geradas dessa entrega.
     ...
   ]
}
```
### [:arrow_right: O que precisa ser feito?](#arrow_right-o-que-precisa-ser-feito)
Estamos planejando desenvolver uma aplicação simples que irá utilizar dados de uma API já disponibilizada pela equipe de desenvolvimento. Nessa aplicação, o usuário terá a capacidade de realizar uma pesquisa utilizando apenas o CPF. O sistema então retornará todas as entregas associadas a esse CPF. Ao selecionar uma entrega específica, exibiremos na tela todos os detalhes relacionados a essa entrega.

Estes detalhes incluem a quantidade de volumes na entrega, informações completas do remetente e destinatário, além de um registro detalhado de todas as etapas de rastreamento. Adicionalmente, a aplicação também apresentará o CNPJ e o nome da transportadora responsável pela entrega selecionada.

Para cumprir esse objetivo, será necessário unir dados de diferentes fontes: alguns provenientes da API das transportadoras e outros relacionados aos dados da entrega. É crucial que esses dados sejam integrados para exibir as informações mencionadas acima.

Um requisito fundamental é implementar um banco de dados para armazenar as informações obtidas após a primeira requisição a qualquer endpoint. Dessa forma, em requisições subsequentes, a aplicação buscará no banco de dados as informações, recorrendo à API somente quando não houver dados previamente armazenados

### [:arrow_right: Observação sobre o teste](arrow_right-observação-sobre-o-teste)
  1. O teste tem como objetivo verificar sua habilidade em lógica de programação, independentemente da experiência prévia. Ele também avaliará seu entendimento sobre assuntos e contextos relacionados às tecnologias web.
   
  2. Fique à vontade para escolher o framework no qual você se sinta mais confortável. Não temos preferência específica neste teste. No entanto, é importante considerar as tecnologias mencionadas na vaga para a qual você está se candidatando. Recomendamos que escolha aquele com o qual você se sinta mais seguro para apresentar e discutir durante a entrevista conosco.
  
  3. No âmbito deste teste, o foco primordial reside na implementação essencial do que foi proposto. Isso implica que a parte visual (front-end) não terá um papel decisivo na avaliação. 

  4. Caso você não consiga completar o teste a tempo do prazo, documente de forma escrita o que não foi terminado e o que você precisaria fazer para terminar. Durante a conversa técnica podemos discutir melhor essa questão. 

## [:dart: Consideramos um diferencial](#dart-consideramos-um-diferencial)
- Uso de Design Patterns
- Uso de Docker
- Uso do desenvolvimento orientado a testes
  

## [:heart: O que será avaliado](#heart-o-que-será-avaliado)
- Elaboração da documentação.
- Garanta que o código seja claro e bem organizado, incluindo uma escolha cuidadosa de nomenclaturas.
- Para candidatos ao cargo sênior, dedique especial atenção ao planejamento da arquitetura.
- Mantenha consistência em suas escolhas e esteja preparado para argumentar sobre as decisões tomadas.
- Demonstre conhecimento e aplicação de padrões, como design patterns e princípios SOLID.
- Apresente soluções nas quais você tem domínio e destaque sua expertise.
- Realize uma modelagem de dados eficiente e coerente.
- Priorize a manutenibilidade do código, facilitando futuras alterações e expansões.
- Implemente um tratamento de erros robusto para garantir a estabilidade do sistema.
- Demonstre cuidado especial com aspectos de segurança ao desenvolver a solução.
- Ao abordar a arquitetura, estruture seu pensamento antes de começar a codificar.
- Demonstre atenção ao desacoplamento de componentes, considerando a segregação em camadas, a utilização de serviços e repositórios, entre outros detalhes.

Let's bora!

## [:smile: Autores](#smile-autores)

| [<img src="https://github.com/guglieelmor.png?size=115" width=115><br><sub>@guglieelmor</sub>](https://github.com/guglieelmor) 
| :---: |
  






