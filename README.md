# Video Opinion Mining

Esse projeto consiste na elaboração de um método capaz de extrair emoções em tempo real de um vídeo, organizando-as em um mapa de calor sobre as dimensões de arousal-valence.

Ele contém uma classe principal, VEMProcessor que com um simples comando já classifica o vídeo quanto à opinião extraída das faces presentes no vídeo, do áudio das falas e da transcrição desse áudio, já gerando mapas de calor para as três categorias e um multimodal envolvendo o áudio e a transcrição.

Também possui outras 5 classes que podem ser customizadas para alterar o processo de extração de opiniões ou a geração do mapa de calor.
<ul>
  <li>VideoSegmenter
    <ul>
      <li>Transforma um arquivo mp4 em um dataframe do Pandas contendo 
      cada frase do vídeo, suas timestamps e o segmento do vídeo que contém a frase</li>
    </ul>
  </li>
  <li>OpinionExtractionModel
    <ul>
      <li>Contém os modelos que serão usados para realizar a extração de opinião da trancrição, áudio e vídeo</li>
    </ul>
  </li>
  <li>OpinionExtractor
    <ul>
      <li>Responsável por aplicar os modelos em cada segmento de vídeo</li>
    </ul>
  </li>
  <li>MultimodalOpinionExtractor
    <ul>
      <li>Extrai opiniões multimodais das classificações já realizadas pelo extrator de opinião da transcrição e do áudio</li>
    </ul>
  </li>
  <li>EmotionMapGenerator
    <ul>
      <li>Gera um heatmap com o dataframe desde que ele tenha sido classificado quanto as emoções. Isso pode ser feito para qualquer modalidade</li>
    </ul>
  </li>
</ul>

  Aqui tem um exemplo de heatmap gerado
<img src="/img/heatmap.png">
Links Importantes

Exemplo de uso do pip [https://colab.research.google.com/drive/1sYAYRxFdpa86Huxm-KVkEvQo6x8ZmgS6?authuser=1#scrollTo=yF78bgHtziJ6](https://colab.research.google.com/drive/1UqzA6bDgtZWGji652a0UjT7ZtDh3Xyi5?authuser=1#scrollTo=CKL-Mm9D18BB)

Apresentação no Canvas explicando o projeto (versão antiga do projeto cahamda VIEMR) [https://www.canva.com/design/DAFy1Pywr0Q/F6_WBK5Bjz12OHZG8P4V8Q/edit](https://www.canva.com/design/DAFy1Pywr0Q/F6_WBK5Bjz12OHZG8P4V8Q/edit)
https://sol.sbc.org.br/index.php/eniac/article/view/25746/25562

Artigo do ENIAC publicado sobre o assunto elaborado pelo colega Gabriel Natal[https://sol.sbc.org.br/index.php/eniac/article/view/25746/25562](https://sol.sbc.org.br/index.php/eniac/article/view/25746/25562)

Fontes para os modelos utilizados:
Github do whisperx(transcrição) [https://github.com/m-bain/whisperX](https://github.com/m-bain/whisperX)
Hugging Face do tradutor da Unicamp [https://huggingface.co/unicamp-dl/translation-pt-en-t5](https://huggingface.co/unicamp-dl/translation-pt-en-t5)
Site oficial do goemotions (texto) [https://blog.research.google/2021/10/goemotions-dataset-for-fine-grained.html?m=1](https://blog.research.google/2021/10/goemotions-dataset-for-fine-grained.html?m=1)
Github contendo a implementação do classificador HUBERT (áudio) [https://github.com/m3hrdadfi/soxan](https://github.com/m3hrdadfi/soxan)
Github do deepface(vídeo) [https://github.com/serengil/deepface](https://github.com/serengil/deepface)
