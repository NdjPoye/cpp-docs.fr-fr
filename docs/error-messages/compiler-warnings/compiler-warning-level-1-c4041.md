---
title: Compilateur avertissement (niveau 1) C4041 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4041
dev_langs: C++
helpviewer_keywords: C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42779d33cad8fc867b08b412d2ded294360a0812
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4041"></a>Avertissement du compilateur (niveau 1) C4041
limite du compilateur : arrêt de la sortie de l’explorateur  
  
 Les informations du navigateur dépassent la limite du compilateur.  
  
 Cet avertissement peut être dû à une compilation avec [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (informations du navigateur comprenant des variables locales).  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Compilez avec /Fr (informations du navigateur sans variables locales).  
  
2.  Désactivez la sortie de navigateur (compilez sans /FR ou /Fr).