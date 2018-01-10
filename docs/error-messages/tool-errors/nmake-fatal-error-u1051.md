---
title: "Erreur irrécupérable NMAKE U1051 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1051
dev_langs: C++
helpviewer_keywords: U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93c109bf723b3c4cf08e998a715fe8f6f33be466
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1051"></a>Erreur irrécupérable NMAKE U1051
Mémoire insuffisante  
  
 NMAKE a manqué de mémoire, y compris de mémoire virtuelle, car le makefile est trop volumineux ou complexe.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Libérez de l’espace sur le disque.  
  
2.  Augmenter la taille du fichier de pagination de Windows NT ou le fichier d’échange Windows.  
  
3.  Si une partie seulement du makefile est utilisée, divisez le makefile en plusieurs fichiers ou utilisez **! IF** pour limiter la quantité NMAKE doit traiter les directives de prétraitement. Le **! IF** sont les suivantes : **! IF**, `!IFDEF`, **! IFNDEF**, **! ELSE IF**, **! AUTRE** `IFDEF`, et **! AUTRE** `IFNDEF`.