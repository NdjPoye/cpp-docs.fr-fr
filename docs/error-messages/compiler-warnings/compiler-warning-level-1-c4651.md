---
title: Compilateur avertissement (niveau 1) C4651 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4651
dev_langs: C++
helpviewer_keywords: C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dce099d657341ebc957c95ab0cd14f508f9e36ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4651"></a>Avertissement du compilateur (niveau 1) C4651
'définition' spécifiée pour l’en-tête précompilé mais non pour la compilation en cours  
  
 La définition a été spécifiée lors de l’en-tête précompilé a été généré, mais pas dans cette compilation.  
  
 La définition soit appliqué à l’intérieur de l’en-tête précompilé, mais pas dans le reste du code.  
  
 Si un en-tête précompilé a été généré avec/DSYMBOL, le compilateur génère cet avertissement si la compilation /Yu ne comprend pas /DSYMBOL.  Ajout de /DSYMBOL à la ligne de commande /Yu résout cet avertissement.