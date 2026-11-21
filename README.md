# reelcomenta

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


[![reelcomenta](guia/assets/banner.jpg)](https://inematds.github.io/reelcomenta/guia/)

**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

## O que Ã©

O reelcomenta Ã© uma ferramenta de linha de comando que pega o link de um reel, TikTok ou Short de outra pessoa e monta um vÃ­deo vertical seu comentando aquele assunto. O vÃ­deo original continua passando, com a mÃºsica dele baixa. O seu avatar do HeyGen fala num canto da tela, os nÃºmeros da sua pesquisa aparecem num painel com a fonte, e o vÃ­deo termina com uma pergunta e a chamada para os cursos gratuitos do inema.club. Ã‰ para quem produz conteÃºdo e quer surfar num vÃ­deo que jÃ¡ estÃ¡ circulando, sem gravar nada. Precisa de Python, ffmpeg, uma conta HeyGen com o seu avatar e dos projetos cardshorts e explicavideos.

## ðŸ“– Guia de uso

Guia completo (landing + passo a passo): **https://inematds.github.io/reelcomenta/guia/**

## O formato

| Tempo | Na tela | Ãudio |
|---|---|---|
| Quadro 0 | data dd/mm/aaaa + manchete + o reel jÃ¡ rodando | mÃºsica do reel, baixa |
| NÃºmeros | painel com contador e fonte, na palavra exata da fala; o melhor trecho do reel em cÃ¢mera lenta | avatar fala, mÃºsica abaixa sozinha |
| Pergunta | "ESPERAR" riscado â†’ "OU SE QUALIFICAR" | "vai ficar esperando ou vai se qualificar?" |
| Fecho | mosaico das capas reais dos cursos + cartÃ£o INEMA.CLUB | "+300 cursos gratuitosâ€¦ comeÃ§a hoje" |

O avatar fica embaixo Ã  direita (400Ã—453, moldura Ã¢mbar e nome), recortado no rosto automaticamente (OpenCV). A legenda vem palavra a palavra, a partir da transcriÃ§Ã£o da prÃ³pria fala do avatar.

## Uso

```bash
python3 reelcomenta.py novo "<link>" --id assunto      # baixa, transcreve, folha de quadros, roteiro.yaml
# escreva edicoes/<data>-assunto/roteiro.yaml (fala + cartÃµes com fonte)
python3 reelcomenta.py previa  edicoes/<pasta>          # previa.jpg com tempo estimado
echo "aprovado" > edicoes/<pasta>/avatar/APROVADO_HEYGEN
python3 reelcomenta.py avatar  edicoes/<pasta>          # estÃºdio do HeyGen, espera e baixa
python3 reelcomenta.py montar  edicoes/<pasta>          # video.mp4
python3 reelcomenta.py conferir edicoes/<pasta>         # conferencia.jpg + volume
python3 reelcomenta.py enviar  edicoes/<pasta> "texto"  # bot do Telegram
```

Exemplo completo: [`edicoes/2026-10-09-robo-trabalho/roteiro.yaml`](edicoes/2026-10-09-robo-trabalho/roteiro.yaml).

Para o Claude Code ou o Codex, a skill estÃ¡ em [`skill/SKILL.md`](skill/SKILL.md): com ela, basta mandar o link.

## DependÃªncias

- Python 3 com Pillow, PyYAML e OpenCV; ffmpeg; yt-dlp.
- [cardshorts](https://github.com/inematds/cardshorts): transcriÃ§Ã£o local com tempo por palavra e envio para o Telegram.
- [explicavideos](https://github.com/inematds/explicavideos): estÃºdio do HeyGen pelo navegador (sem API de geraÃ§Ã£o) e leitura de status.
- Caminhos por variÃ¡vel: `RC_CARDSHORTS`, `RC_EXPLICAVIDEOS`, `RC_PERFIL_HEYGEN`, `RC_TEMPLATE_HEYGEN`, `RC_PORTAL_DADOS`, `RC_CAPAS`, `RC_MUSICA`, `RC_DISPLAY`.

## EdiÃ§Ãµes

| Data | EdiÃ§Ã£o | O que mostra |
|---|---|---|
| 09/10/2026 | `edicoes/2026-10-09-robo-trabalho` | robÃ´ danÃ§ando no palco â†’ 92 milhÃµes de empregos (FÃ³rum EconÃ´mico Mundial), 41% das empresas, 1 em 5 cortando gerÃªncia mÃ©dia (Gartner), 542 mil robÃ´s (IFR) |

LicenÃ§a MIT. O vÃ­deo de terceiro usado em cada ediÃ§Ã£o continua sendo do seu autor; os nÃºmeros seguem as fontes citadas.

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>