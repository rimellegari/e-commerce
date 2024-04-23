# NLP aplicado para análise de sentimentos de comentários de clientes de um e-commerce brasileiro: Um estudo comparativo de performance de de modelos, entre Árvore de Decisão e Naive Bayes
## *NLP sentiment analysis applied to customers review in a Brazilian e-commerce:  A model  compairson study between Decision Tree and Naive Bayes*
<h2>Introdução</h2>

<p>A voz do cliente é a principal fonte para insights e melhorar a satisfação de clientes e com grandes plataformas de comércio eletrônico, revisar centenas e até milhares de comentários pode ser tornar um desafio. Nesse contexto, ter um modelo de análise de sentimento preciso garante que a informação chegue ao time responsável mais rapidamente e que eles consigam trabalhar para melhorar os processos, impactando na satisfação do consumidor e consequentemente no faturamento</p>

<i>
    <h2>Introduction</h2>
        <p>The voice of the customer is the source for insights and improving in customer satisfaction and with big e-commerce platforms analyze thousands of customer reviews may become a challenge. Having an accurate sentiment analysis, ensures that data gets to the responsible team much faster and that they can work to improve processes, impacting on customer satiscation and therefore on the revenue.</p>
</i>



<h2>Objetivo do projeto</h2>
<h3>Perspectiva de negócio</h3>
<p>O projeto tem como objetivo responder a três perguntas principais</p>
    <ul>
        <li>Qual é o valor de compra médio?</li>
        <li>Quais são as categorias de produtos mais vendidas?</li>
        <li>É possível criar um modelo de classifacção baseado em NLP para classificar comentários de produtos?</li>
    </ul>
<h3>Perspectiva técnica</h3>
 <p> De uma perspectiva técnica o projeto visa:<p>
    <ul>
        <li>Extração e tratamento de dados, entedendo quais informações são relevantes para responder as perguntas do negócio</li>
        <li>Realizar uma análise exploratória dos dados e consolidação dos resultados e explorar os recursos gráficos do seaborn para criação de visualizações mais engajadoras</li>
        <li>Compreender o processo de análise de sentimento com Processamento de Linguagem Natural (PLN)consistindo em:</li>
            <li>
                <ol>
                    <li>Tratamento do texto e remoção de stopwords(remoção de palavras sem valor semântico) com uso de NLTK e Spacy<li>
                    <li>Transformação de palavras em vetores comparando a eficiência de duas técnicas distintas <i>Bag-of-words</i> e </i>Term Frequency- Inverse Document Frequency (TF-IDF)</i></li>
                    <li>Uso do scikit-learn  para testar  dois modelos de análise de sentimento (Naive-Bayes e Árvore de Decisão)</li>
                    <li>Interpretar e comparar a acurácia dos modelos usando recursos do scikit learn e visualização da matriz de confusão</li>
                </ol>
            </li>
        <li>Avaliar a viabilidade do modelo testado e em caso positivo, embasar a escolha de um dos modelos</li>
    </ul>

<i>
    <h2>Project objective</h2>
    <h3>Business perspective</h3>
    <p>This project aims to answer three main questions</p>
        <ul>
            <li>What's the average order value?</li>
            <li>What are the best-selling product categories?</li>
            <li>Is it possible to create a NLP based classification model able to classify a review into good or bad (sentiment analysis)?</li>
        </ul>
    <h3>Techincal perspective</h3>
        <p>From a technical perspective, the project aims to:</p>
        <ul>
        <li>Data extraction and treatment, understanding which datapoints are relevant to answer business questions</li>
        <li> Perform an EDA, consolidating results in charts and exploring seaborn resources to create engaging charts (improve data visualization skills) </li>
        <li>Understand and apply sentiment analysis with Natural Language Processing (NLP) process which consists in:</li>
            <li>
                <ol>
                    <li>Text cleaning and stopwords removal(remove words that do not contain any semantical value for the NLP model semântico) byusing NLTK and Spacy<li>
                    <li>Feature extraction comparing the efficieny between two techniques  <i>Bag-of-words</i> and </i>Term Frequency- Inverse Document Frequency (TF-IDF)</i></li>
                    <li>Use scikit-learn to evaluate two NLP tecniques (Naive-Bayes and Decision Tree)</li>
                    <li>Analyze and compare the accuracy of the models with features from sckit-learn and confusion matrix interpretation</li>
                </ol>
            </li>
        <li>Evaluate model viablity and if postive, justify the choice of the model</li>
    </ul>

</i>
<h2>Fonte dos dados</h2>
<p>O dataset usado para esse projeto encontra-se disponível em https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce. 
<i>
    <h2>Data source</h2>
    <p>The dataset used for this project is available at https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce.</p>
</i>
<h2>Metodologia</h2>
    <p>Para análises relacionadas ao valor médio do pedido e aos produtos mais vendidos, verificou-se se os IDs dos pedidos de compra eram únicos para não contar a mesma compra duas vezes. Todas as informações de pagamento estavam completas. Para a parte de PLN do projeto, as avaliações com menos de 3 dígitos ou vazias foram descartadas, pois não têm valor semântico. Além disso, palavras com até 10 caracteres (usadas para expressar sentimentos como bom, satisfeito, etc.) foram analisadas e um dicionário em Python foi criado para corrigi-las em todas as avaliações. Apenas avaliações com classificação e preenchimento adequados foram usadas no modelo. Como a satisfação média do cliente é 3.6 e o cliente só pode dar notas de 1, 2, 3, 4 ou 5, as classificações 4 e 5 foram consideradas positivas, enquanto o restante foi considerado negativo.</p>
    <p>O método de NLP proposto foi baseado no trabalhos de Krishna (2018) e Akuma (2022). Ambos os autores utilizam mais de um método de vetorização e algoritmo de classificação para encontrar um modelo com melhor precisão. Para este estudo, o texto foi pré-processado removendo pontuação, stopwords (como artigos e preposições) e vetorizado empregando duas técnicas diferentes: Bag of Words (as palavras são representadas com base em sua multiplicidade, desconsiderando gramática e ordem das palavras) e Term Frequency-Inverse Document Frequency (TF-IDF), que indica se uma palavra é comum ou rara em todas as avaliações. O conjunto de dados foi dividido em conjuntos de teste e treinamento e dois algoritmos de classificação foram utilizados, Naïve Bayes e Árvore de Decisão, totalizando 4 testes. O melhor método foi escolhido com base na precisão e análise da matriz de confusão
    </p>
    <h2>Methodology</h2>
    <p>For analysis related to average order value and best selling products it was checked if purchase orders id were unique to not count the same purchase twice. All payment information was complete. For the NLP part of the project reviews with less than 3 digits or empty were discarded as they have no semantic value. In addition to this, words until 10 characters (charactes used to express sentiments such as good, satisfied and so on) were analysed and a python dictionary was created to correct them in all reviews. Only reviews with rating and properly filled were used on the model. As the average satisfaction of the customer is 3.6, and the customer can only score in 1,2,3,4 or 5, ratings 4 and 5 were considered positive, while the rest negative.
    </p>
    <p>The proposed NLP method was based on Krishna (2018) Akuma (2022) work. Both authors use more than one vectorizing method and classification algorithm to find a model with better accuracy. For this study, text was preprocessed by removing punctuation, stopwords (such as articles and preposition) and vectorized employing two different techniques Bag of Words (words are represented based on their multiplicty disregarding grammar and word order) and Term Frequency-Inverse Document Frequency (TF-IDF) which indicates if a word is common or rare across all reviews. The dataset was split into test and training sets and two classification algorithms were used, Naïve Bayes and Decision Tree, totalizing 4 tests, the best method was chosen based on accuracy and confusion matrix analysis.
    </p>
</i>
<h2>Resultados</h2>
<i><h2>Results</h2></i>
    <p></p>

</i>   
    <p></p>
</i>

<p></p>

</i>
    <p></p>
</i>



<h2>Conclusão</h2>
    <p></p> 

<i>
    <h2>Conclusion</h2>
    <p></p>

</i>

<h2>Referências</h2>
    <p>
    AKUMA, S.; LUBEM, T.; ADOM, I.; “Comparing Bag of Words and TF-IDF with different models for hate speech detection from live tweets”, 2022. (PDF) Comparing Bag of Words and TF-IDF with different models for hate speech detection from live tweets (researchgate.net) https://www.researchgate.net/publication/363759715_Comparing_Bag_of_Words_and_TF-IDF_with_different_models_for_hate_speech_detection_from_live_tweets
    <p>
    <p>
    KRISHA, A.;AICH, A.; V, A.; HEGDE, C. “Analysis of Customer Opinion Using Machine Learning and NLP Techniques”, 2018. Analysis of Customer Opinion Using Machine Learning and NLP Techniques by Akshay Krishna, Animikh Aich, Akhilesh V, Chetana Hegde :: SSRN https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3315430
    </p>


<i>
    <h2>Reference</h2>
         <p>
            AKUMA, S.; LUBEM, T.; ADOM, I.; “Comparing Bag of Words and TF-IDF with different models for hate speech detection from live tweets”, 2022. (PDF) Comparing Bag of Words and TF-IDF with different models for hate speech detection from live tweets (researchgate.net) https://www.researchgate.net/publication/363759715_Comparing_Bag_of_Words_and_TF-IDF_with_different_models_for_hate_speech_detection_from_live_tweets
        </p>
        <p>
            KRISHA, A.;AICH, A.; V, A.; HEGDE, C. “Analysis of Customer Opinion Using Machine Learning and NLP Techniques”, 2018. Analysis of Customer Opinion Using Machine Learning and NLP Techniques by Akshay Krishna, Animikh Aich, Akhilesh V, Chetana Hegde :: SSRN https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3315430
        </p>

</i>