---
title: Avertissement NMAKE U4011 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U4011
dev_langs:
- C++
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ae15a3912fe3172e9dec98e1a90a3a262c47117
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-warning-u4011"></a>Avertissement NMAKE U4011
'target' : les dépendants pas tous disponibles ; cible non générée  
  
 Un dépendant de la cible spécifiée n’existe pas ou était obsolète, et une commande de mise à jour du dépendant a retourné un code de sortie différent de zéro. L’option /K a indiqué à NMAKE de poursuivre le traitement des parties non liées de la génération et d’émettre un code de sortie 1 quand la session NMAKE est terminée.  
  
 Cet avertissement est précédé par l’avertissement [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) pour chaque dépendant qui n’a pas pu être créé ou mis à jour.