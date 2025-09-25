**Fonte de dados:** {DATA_ORIGIN}  
**Pares pós-filtro:** {len(pairs)}  
**BLEU (subset teste):** {bleu_mean:.4f}  
_Gerado em:_ {datetime.utcnow().isoformat()}Z

## Exercícios 9.5.7

Fonte de dados: opus100 (HF)
Pares pós-filtro: 48981
BLEU (subset teste): 0.0750
Gerado em: 2025-09-22T14:18:23.025977Z

Exercícios 9.5.7
1) Efeito de num_examples nos vocabulários
Tokenização por palavra (normalização simples), min_freq=2.

num_examples	vocab_src	vocab_tgt
500	320	308
1000	565	573
2000	1063	1052
6000	2827	3079
10000	4393	5003
20000	7423	8765
Observações:

Com mais exemplos, os vocabulários crescem de forma sublinear (ganhos marginais decrescentes), compatível com Zipf.
O vocabulário pt tende a ficar maior que en em ENG→POR, por morfologia e acentuação, o que fragmenta mais o léxico quando tokenizamos por palavra.
Ajustar min_freq e/ou limitar o vocabulário reduz sparsidade e OOV.
2) Idiomas sem separadores (ex.: chinês/japonês) devem usar palavra?
Preferível usar subpalavras (BPE/WordPiece/SentencePiece) em vez de palavras.
Motivos: melhor cobertura de OOV, robustez para escritas contínuas e morfologia rica, e vocabulário menor com expressividade suficiente.

Leituras sugeridas: D2L (cap. de tradução), Sennrich et al. 2016 (BPE), Kudo 2018 (SentencePiece).