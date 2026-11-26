ï»¿# reelcomenta

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


[![reelcomenta](guia/assets/banner.jpg)](https://inematds.github.io/reelcomenta/guia/)

**ê°Å¸â¡Â§ê°Å¸â¡Â· [PortuguêÂªs](README.md) êÂ· ê°Å¸â¡Âºê°Å¸â¡Â¸ [English](README.en.md) êÂ· ê°Å¸â¡Âªê°Å¸â¡Â¸ [EspaêÂ±ol](README.es.md)**

## O que êÂ©

O reelcomenta êÂ© uma ferramenta de linha de comando que pega o link de um reel, TikTok ou Short de outra pessoa e monta um vêÂ­deo vertical seu comentando aquele assunto. O vêÂ­deo original continua passando, com a mêÂºsica dele baixa. O seu avatar do HeyGen fala num canto da tela, os nêÂºmeros da sua pesquisa aparecem num painel com a fonte, e o vêÂ­deo termina com uma pergunta e a chamada para os cursos gratuitos do inema.club. êâ° para quem produz conteêÂºdo e quer surfar num vêÂ­deo que jêÂ¡ estêÂ¡ circulando, sem gravar nada. Precisa de Python, ffmpeg, uma conta HeyGen com o seu avatar e dos projetos cardshorts e explicavideos.

## ê°Å¸ââ Guia de uso

Guia completo (landing + passo a passo): **https://inematds.github.io/reelcomenta/guia/**

## O formato

| Tempo | Na tela | êÂudio |
|---|---|---|
| Quadro 0 | data dd/mm/aaaa + manchete + o reel jêÂ¡ rodando | mêÂºsica do reel, baixa |
| NêÂºmeros | painel com contador e fonte, na palavra exata da fala; o melhor trecho do reel em cêÂ¢mera lenta | avatar fala, mêÂºsica abaixa sozinha |
| Pergunta | "ESPERAR" riscado ê¢â â "OU SE QUALIFICAR" | "vai ficar esperando ou vai se qualificar?" |
| Fecho | mosaico das capas reais dos cursos + cartêÂ£o INEMA.CLUB | "+300 cursos gratuitosê¢â¬Â¦ comeêÂ§a hoje" |

O avatar fica embaixo êÂ  direita (400êâ453, moldura êÂ¢mbar e nome), recortado no rosto automaticamente (OpenCV). A legenda vem palavra a palavra, a partir da transcriêÂ§êÂ£o da prêÂ³pria fala do avatar.

## Uso

```bash
python3 reelcomenta.py novo "<link>" --id assunto      # baixa, transcreve, folha de quadros, roteiro.yaml
# escreva edicoes/<data>-assunto/roteiro.yaml (fala + cartêÂµes com fonte)
python3 reelcomenta.py previa  edicoes/<pasta>          # previa.jpg com tempo estimado
echo "aprovado" > edicoes/<pasta>/avatar/APROVADO_HEYGEN
python3 reelcomenta.py avatar  edicoes/<pasta>          # estêÂºdio do HeyGen, espera e baixa
python3 reelcomenta.py montar  edicoes/<pasta>          # video.mp4
python3 reelcomenta.py conferir edicoes/<pasta>         # conferencia.jpg + volume
python3 reelcomenta.py enviar  edicoes/<pasta> "texto"  # bot do Telegram
```

Exemplo completo: [`edicoes/2026-10-09-robo-trabalho/roteiro.yaml`](edicoes/2026-10-09-robo-trabalho/roteiro.yaml).

Para o Claude Code ou o Codex, a skill estêÂ¡ em [`skill/SKILL.md`](skill/SKILL.md): com ela, basta mandar o link.

## DependêÂªncias

- Python 3 com Pillow, PyYAML e OpenCV; ffmpeg; yt-dlp.
- [cardshorts](https://github.com/inematds/cardshorts): transcriêÂ§êÂ£o local com tempo por palavra e envio para o Telegram.
- [explicavideos](https://github.com/inematds/explicavideos): estêÂºdio do HeyGen pelo navegador (sem API de geraêÂ§êÂ£o) e leitura de status.
- Caminhos por variêÂ¡vel: `RC_CARDSHORTS`, `RC_EXPLICAVIDEOS`, `RC_PERFIL_HEYGEN`, `RC_TEMPLATE_HEYGEN`, `RC_PORTAL_DADOS`, `RC_CAPAS`, `RC_MUSICA`, `RC_DISPLAY`.

## EdiêÂ§êÂµes

| Data | EdiêÂ§êÂ£o | O que mostra |
|---|---|---|
| 09/10/2026 | `edicoes/2026-10-09-robo-trabalho` | robêÂ´ danêÂ§ando no palco ê¢â â 92 milhêÂµes de empregos (FêÂ³rum EconêÂ´mico Mundial), 41% das empresas, 1 em 5 cortando gerêÂªncia mêÂ©dia (Gartner), 542 mil robêÂ´s (IFR) |

LicenêÂ§a MIT. O vêÂ­deo de terceiro usado em cada ediêÂ§êÂ£o continua sendo do seu autor; os nêÂºmeros seguem as fontes citadas.

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>