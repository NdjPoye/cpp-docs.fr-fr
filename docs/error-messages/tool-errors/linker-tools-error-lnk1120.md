---
title: "L’erreur LNK1120 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1120
dev_langs: C++
helpviewer_keywords: LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82fb2f290bc0aeaf8332e642c014006d38b5c97d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1120"></a>Erreur des outils Éditeur de liens LNK1120
*nombre* externes non résolus  
  
L’erreur LNK1120 indique le nombre (*nombre*) d’erreurs de symbole externe non résolu pour cette opération de liaison. La plupart non résolue de symbole externe les erreurs sont signalées individuellement par [erreur des outils Éditeur de liens LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md) et [erreur des outils Éditeur de liens LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), qui précède ce message d’erreur, une fois pour chaque symbole externe non résolu Erreur de symbole.  
  
Pour corriger cette erreur, corrigez toutes les autres erreurs externes non résolues ou d’autres erreurs de l’éditeur de liens qui la précèdent dans la sortie de génération. Cette erreur n’est pas signalée lorsqu’il ne reste aucune erreur externe non résolu.  
