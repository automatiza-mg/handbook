---
date: 2024-07-24
authors: [gabrielbdornas]
draft: False
comments: true
categories:
  - Ferramentas
---

# Como utilizar Python para cortar vídeos :material-content-cut:

Durante a criação do post de nosso [Webnar 8](./20240712_webnar_automatiza_mg_8.md), surgiu a necessidade de cortarmos um pedaço do vídeo.
Pesquisei sem sucesso ferramentas GUI para tal e resolvi criar um script Python para resolver o problema.
Acredito que o resultado ficou bem legal!

<!-- more -->

Após uma pesquisa rápida no google, encontrei [esta resposta stackoverflow](https://stackoverflow.com/a/49697025/11755155) sugerindo o seguinte código:

```python
from moviepy.video.io.ffmpeg_tools import ffmpeg_extract_subclip
ffmpeg_extract_subclip("video1.mp4", t1, t2, targetname="test.mp4")
```

Busquei então a lib `moviepy` no [Pypi](https://pypi.org) e encontrei a versão [1.0.3](https://pypi.org/project/moviepy/1.0.3/), atualizada pela última vez em 07/05/2020. Resolvi utilizar esta versão pois o post stackoverflow citado acima foi escrito em 2018, então tentei utilizar a versão mais próxima para evitar erros.

Fiz pequenas modificações no código, incluindo variáveis para os caminhos dos arquivos de entrada e saída e o resultado foi:

```python
from pathlib import Path
from moviepy.video.io.ffmpeg_tools import ffmpeg_extract_subclip

path = Path(__file__).parent
video_name = 'webnar_8.mp4' # mudar nome do audio
video_path = path / 'arquivos' / video_name
cut_video_path = path / 'webnar_8_cortado.mp4'
# in seconds
time_start = 0
time_end = 10
```

Por fim, melhorei as variáveis `time_start` e `time_end` para não precisar fazer a conta manual do número de segundos, tendo em vista que a informação que tinha estava no formato de hora `hh:mm:ss` (Neste ponto pedi uma ajudinha p chatGPT). Código revisado:

```python
from pathlib import Path
from moviepy.video.io.ffmpeg_tools import ffmpeg_extract_subclip
from datetime import datetime, timedelta

def time_to_seconds(time_str):
    time_obj = datetime.strptime(time_str, '%H:%M:%S')
    delta = timedelta(hours=time_obj.hour, minutes=time_obj.minute, seconds=time_obj.second)
    return delta.total_seconds()

path = Path(__file__).parent
video_name = 'webnar_8.mp4' # mudar nome do audio
video_path = path / 'arquivos' / video_name
cut_video_path = path / 'webnar_8_cortado.mp4'
# hh:mm:ss
time_start = time_to_seconds('00:00:00')
time_end = time_to_seconds('02:40:00')

ffmpeg_extract_subclip(
    video_path,
    time_start,
    time_end,
    targetname=cut_video_path)
```

Deste modo, da próxima vez que precisar utilizar o código basta trocar os caminhos de entrada e saída, bem como os tempos iniciais e finais do vídeo.

Uma observação importante a ser feita é a utilização de um container docker para rodar o script, tendo em vista a necessidade de instalação da ferramenta `ffmpeg`, que não queria fazer diretamente na minha máquina.

Para rodar, acionei o container via `task container`[^1] e dentro do container[^2] rodei `pip install -r requirements.txt` e `python main.py`.

## Referência

- [Código gerado](https://github.com/gabrielbdornas/open-reprex/tree/9fad0d09256d3a8d5a3320cf957410f9e45fb6c5/202407251440_cortar_video).

[^1]: Task criada com auxílio da biblioteca [taskipy](https://pypi.org/project/taskipy/).
[^2]: Caso seja a primeira vez utilizando o script, poderá ser necessário rodar `task image` antes de `task container`.
