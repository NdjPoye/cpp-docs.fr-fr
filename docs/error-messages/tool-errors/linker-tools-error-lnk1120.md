---
title: "L’erreur LNK1120 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1120
dev_langs:
- C++
helpviewer_keywords:
- LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: dafecac08499bea0571b2f48015e50570229d889
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="linker-tools-error-lnk1120"></a>Erreur des outils Éditeur de liens LNK1120
*nombre* externes non résolus  
  
L’erreur LNK1120 indique le nombre (*nombre*) d’erreurs de symbole externe non résolu pour cette opération de liaison. La plupart non résolue de symbole externe les erreurs sont signalées individuellement par [erreur des outils Éditeur de liens LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md) et [erreur des outils Éditeur de liens LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), qui précède ce message d’erreur, une fois pour chaque symbole externe non résolu Erreur de symbole.  
  
Pour corriger cette erreur, corrigez toutes les autres erreurs externes non résolues ou d’autres erreurs de l’éditeur de liens qui la précèdent dans la sortie de génération. Cette erreur n’est pas signalée lorsqu’il ne reste aucune erreur externe non résolu.  

