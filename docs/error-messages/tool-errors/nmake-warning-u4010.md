---
title: Avertissement NMAKE U4010 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U4010
dev_langs: C++
helpviewer_keywords: U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1b2d90e95a3417241991eb01f0ec718d75cd8558
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-warning-u4010"></a>Avertissement NMAKE U4010
'target' : build a échoué ; /K spécifié, suite...  
  
 Une commande dans le bloc de commandes de la cible donnée a retourné un code de sortie différent de zéro. L’option /K a indiqué à NMAKE de poursuivre le traitement des parties non liées de la génération et d’émettre un code de sortie 1 quand la session NMAKE est terminée.  
  
 Si la cible donnée est elle-même dépendante d’une autre cible, NMAKE émet un avertissement [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) après cet avertissement.