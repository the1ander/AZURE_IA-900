# Guia completo cadastro e uso da Automated Machine Learning no Azure Machine Learning

 <strong> Este repositório documenta minha jornada de instalação e configuração da Automated Machine Learning (AutoML) no Azure Machine Learning </strong>.
 Deixo neste repositório um guia passo a passo detalhado para quem deseja implementar soluções de AutoML na nuvem. Desde a configuração inicial do ambiente Azure até a execução de experimentos de AutoML e interpretação de resultados, compartilho insights, dicas e melhores práticas aprendidas ao longo do caminho. Se você é novo no Azure Machine Learning ou procura aprimorar suas habilidades em AutoML, este repositório serve como um recurso valioso para acelerar seu aprendizado e implementação eficaz.

### Instalando e configurando meu ambiente Machine Learning Automatizado no Azure Machine Learning

![image](https://github.com/the1ander/AZURE_IA-900/assets/151629165/8399438c-5c9c-4aa7-a97e-fa139108a135)



## Passo 1: Acessar o Portal do Azure

Primeiramente abra seu navegador e digite o endereço https://portal.azure.com
<p>Neste passo, Você precisará entrar com suas credenciais da Microsoft. Isso inclui seu e-mail e senha associados à sua conta do Azure.

## Passo 1: Criar um Novo Recurso de Machine Learning

<p>No portal do Azure, procure pelo botão "+ Criar um recurso". Clique nele.</p>
<p>Na barra de pesquisa que aparece, digite "Machine Learning" e selecione a opção correspondente. </p>
<p>Utilize as configurações recomendadas no portal Microsoft:
<p> https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html </p>
<ul>
  <li>Assinatura : sua assinatura do Azure. </li>
  <li>Grupo de recursos : Crie ou selecione um grupo de recursos ( pode nomear da forma q mais convem)  .</li>
  <li>Nome : Insira um nome exclusivo para seu espaço de trabalho .</li>
  <li>Região : Selecione a região geográfica mais próxima .</li>
 <p>OBSERVAÇÃO SOBRE REGIÃO: Por motivo de valor cobrado por serviços o uso escolha pessoal foi <strong>"East USA"</strong></p>
   <li>Conta de armazenamento : "NÃO ALTEREI" (mantive o escolhido automaticamente) .</li>
   <li>Cofre de chaves : "NÃO ALTEREI" (mantive o escolhido automaticamente) .</li>
   <li>Insights de aplicativos : "NÃO ALTEREI" (mantive o escolhido automaticamente) .</li>
</ul>

##### Não alterei as opções adicionais de configuração como: NetWorking | Encryption | Tags |
![image](https://github.com/the1ander/AZURE_IA-900/assets/151629165/878969aa-da08-4724-ab17-03cab960e0ec)


## Passo 3: Finalizar a Criação do Espaço de Trabalho

<p>Após configurar as opções, selecione "Revisar + criar" e depois "Criar".</p>
<p> Aguarde alguns minutos até que o espaço de trabalho seja criado. Você pode acompanhar o progresso na tela.</p>

## Passo 4: Acessar o Azure Machine Learning Studio
<p> Uma vez que o espaço de trabalho esteja pronto, clique em "Launch Studio" ou abra uma nova guia e entre com a mesma conta da Microsoft. Se aparecerem mensagens iniciais, feche-as para limpar a tela. </p>


# Configurando o Treinamento do nosso Modelo


## Passo 1: Início Rápido no Azure Machine Learning Studio

Finalizado o processo anterior aperte no botão <strong>"Go to resource"</strong> para ( Acessar o seu laboratório).

![image](https://github.com/the1ander/AZURE_IA-900/assets/151629165/8d6cbcac-acd6-4cb9-b9f7-35a058d75411)


Finalizado o processo anterior e acessado o seu laboratório, seguida você vai ser encaminhado para o Azure Machine Learning Studio
Objetivo: Preparar-se para criar um novo trabalho de ML automatizado.
<p>Clique em  <strong>"Launch studio"</strong> para ( Acessar o seu estudio de ML).</p>

![image](https://github.com/the1ander/AZURE_IA-900/assets/151629165/2caba2a6-2937-4065-adc5-2d85f12ab421)

## Passo 2: Criando um Novo Trabalho de ML Automatizado
<p>Clique para iniciar um novo trabalho de ML automatizado.</p>

### Detalhes das Configurações Básicas:
<ul>
 <li> <strong>Nome do trabalho:</strong> mslearn-bike-automl. </li>
 <li><strong>Novo nome do experimento:</strong> mslearn-bike-rental.</li>
 <li><strong>Descrição:</strong> "Aprendizado de máquina automatizado para previsão de aluguel de bicicletas".</li>
 <li><strong>Marcadores:</strong> Deixe em branco, a menos que deseje organizar seus trabalhos com tags específicas.</li>
</ul>

## Passo 3: Tipo de Tarefa e Dados
<ul>
 <li>Seleção de Tarefa: Escolha "Regressão" como o tipo de tarefa. Isso é porque o objetivo é prever um número (aluguéis de bicicleta), que é uma tarefa de regressão.</li>
 <li>Conjunto de Dados: Crie um novo conjunto de dados com as seguintes especificações:</li>
 <ol>
  <li>Tipo de Dados: Tabular.</li>
  <li>Fonte de Dados: Escolha "Dos arquivos da web" e use a URL: https://aka.ms/bike-rentals.</li>
  <li>Formato de Arquivo: Certifique-se de que está definido como Delimitado, com vírgula como delimitador e UTF-8 como codificação.</li>
 </ol>
</ul>

## Passo 4:  Configurações de Tarefa
### Detalhes Importantes:
<ul>
 <li><strong>Métrica Primária:</strong> Escolha "raiz do erro quadrático médio normalizado" para avaliar o desempenho do modelo.</li>
 <li><strong>Modelos Permitidos:</strong> Limite os modelos a RandomForest e LightGBM para simplificar e acelerar o treinamento.</li>
</ul>
![image](https://github.com/the1ander/AZURE_IA-900/assets/151629165/0a276a8e-7162-4231-b4bd-3ace81b06546)



## Passo 5: Limites e Cálculo
<p>Configure os limites de teste para controlar a duração e os recursos do treinamento. Por exemplo, defina um máximo de 3 testes e testes simultâneos, com um limite de pontuação da métrica de 0,085.</p>
<ul>
 <li><strong>Seleção de Computação:</strong> Escolha o tipo de computação sem servidor e configure a máquina virtual conforme necessário.</li>
</ul>

