---
title: "L’erreur LNK1120 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 1809ed4e5950165d6a187fd3c62871c25124663f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="linker-tools-error-lnk1120"></a>Erreur des outils Éditeur de liens LNK1120
*nombre* externes non résolus  
  
L’erreur LNK1120 indique le nombre (*nombre*) d’erreurs de symbole externe non résolu pour cette opération de liaison. La plupart non résolue de symbole externe les erreurs sont signalées individuellement par [erreur des outils Éditeur de liens LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md) et [erreur des outils Éditeur de liens LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), qui précède ce message d’erreur, une fois pour chaque non résolus erreur de symbole externe.  
  
Pour corriger cette erreur, corrigez toutes les autres erreurs externes non résolues ou d’autres erreurs de l’éditeur de liens qui la précèdent dans la sortie de génération. Cette erreur n’est pas signalée lorsqu’il ne reste aucune erreur externe non résolu.  

