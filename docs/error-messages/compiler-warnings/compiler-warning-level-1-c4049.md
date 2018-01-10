---
title: Compilateur avertissement (niveau 1) C4049 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4049
dev_langs: C++
helpviewer_keywords: C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15d76be8cdf9855435094d02be5bc28fe27fe89a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4049"></a>Compilateur avertissement (niveau 1) C4049
limite du compilateur : arrêt de l’émission de numéros de ligne  
  
 Le fichier contient plus de 16 777 215 (2<sup>24</sup>-1) lignes sources. Le compilateur arrête la numérotation à 16 777 215.  
  
 Pour le code après la ligne 16 777 215 :  
  
-   L’image ne contient aucune information de débogage pour les numéros de ligne.  
  
-   Certains diagnostics peuvent être signalés avec des numéros de ligne.  
  
-   listes .asm (/ FA) peut avoir des numéros de ligne.