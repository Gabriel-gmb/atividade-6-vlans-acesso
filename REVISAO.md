# Revisão da atividade 6

A revisão confrontou o enunciado apresentado, as cinco capturas fornecidas e as configurações internas do `.pkt`. Não foi executada uma nova simulação no Packet Tracer.

## Verificações do arquivo

| Switch | VLAN 10 | VLAN 20 | Fa0/1 | Fa0/2 | Running igual a startup |
|---|---|---|---|---|---|
| SW-EDGE-01 | Alunos | Visitantes | access / 10 | access / 20 | Sim |
| SW-EDGE-02 | Alunos | Visitantes | access / 10 | access / 20 | Sim |
| SW-EDGE-03 | Alunos | Visitantes | access / 10 | access / 20 | Sim |
| SW-EDGE-04 | Alunos | Visitantes | access / 10 | access / 20 | Sim |

As conexões confirmam PC0–PC3 nas Fa0/1 e Laptop0–Laptop3 nas Fa0/2 dos respectivos switches. As interfaces GigabitEthernet0/1 continuam como interligação à distribuição, sem configuração explícita de trunk nesta entrega. O Server0 permanece na Gi0/2 do SW-EDGE-01 e não foi incluído nas VLANs da atividade.

## Evidências

As quatro capturas de `show vlan brief` mostram VLAN 10 Alunos na Fa0/1 e VLAN 20 Visitantes na Fa0/2. A captura do PC0 mostra duas tentativas de ping para 192.168.10.20, ambas com quatro pacotes enviados e zero recebidos. Esse resultado é compatível com a segmentação configurada, embora um ping sem resposta isoladamente não prove sua causa; as configurações e as tabelas de VLAN complementam a evidência.

## Conclusão e complemento documental

Nenhuma configuração obrigatória ausente foi identificada para o escopo do enunciado da atividade 6: criar as duas VLANs nos switches de acesso e associar as portas dos computadores e notebooks conforme sua paridade. As configurações das interfaces dos quatro switches de acesso estão salvas em startup-config.

Uma captura adicional da topologia completa, sem janelas sobrepostas, é recomendável para melhorar a apresentação; não consta como requisito expresso nos prints do enunciado recebidos. As imagens atuais não mostram um teste de sucesso anterior à segmentação nem dois hosts na mesma VLAN do mesmo switch; não se afirma que esses testes foram realizados.

Trunks, EtherChannels, roteamento entre VLANs e configuração do roteador pertencem a outras etapas. A ausência das VLANs 10/20 no núcleo e na distribuição não é pendência da atividade 6. Os IPs 192.168.10.x/24 foram preservados conforme a prática para evidenciar que a separação por VLAN independe de os hosts usarem a mesma faixa IPv4.
