---
title: Compilateur avertissement (niveau 1) C4657 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4657
dev_langs:
- C++
helpviewer_keywords:
- C4657
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ea95a34b66efef13f38eb160584452947699817
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4657"></a>Avertissement du compilateur (niveau 1) C4657
l’expression implique un type de données postérieur à la dernière génération  
  
 Vous avez ajouté ou modifié un type de données, ce qui le rend nouveau pour votre code source depuis la dernière génération réussie. Modifier & Continuer ne prend pas en charge les modifications sur les types de données existants.  
  
 Cet avertissement sera toujours suivi d’une [Erreur irrécupérable C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Pour plus d’informations, consultez [Modifications de code prises en charge](/visualstudio/debugger/supported-code-changes-cpp).  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Pour supprimer cet avertissement sans mettre fin à la session de débogage en cours  
  
1.  Replacez le type de données dans l’état où il se trouvait avant l’erreur.  
  
2.  Dans le menu **Déboguer** , choisissez **Appliquer les modifications du code**.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>Pour supprimer cette erreur sans modifier votre code source  
  
1.  Dans le menu **Déboguer** , choisissez **Arrêter le débogage**.  
  
2.  Dans le menu **Générer** , cliquez sur **Générer**.