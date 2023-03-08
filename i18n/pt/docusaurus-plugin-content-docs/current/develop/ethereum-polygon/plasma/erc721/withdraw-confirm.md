---
id: withdraw-confirm
title: withdrawChallenge
keywords:
- 'plasma client, erc721, withdrawChallenge, polygon, sdk'
description: 'Introdução ao maticjs'
---

# withdrawConfirm {#withdrawconfirm}

O método `withdrawConfirm` é a segunda etapa do processo de retirada de plasma. Nesta etapa, a prova da sua transação de burn (primeira transação) é submetida e é criado um token ERC-721 de valor equivalente.

Após este processo obter êxito, o período de desafio é iniciado e, após a conclusão do período de desafio, o utilizador pode obter de volta o valor retirado na sua conta na ROOT chain.

O período de desafio é de 7 dias na mainnet.

```
const erc721Token = plasmaClient.erc721(<token address>, true);

const result = await erc721Token.withdrawConfirm(<burn tx hash>);

const txHash = await result.getTransactionHash();

const txReceipt = await result.getReceipt();

```