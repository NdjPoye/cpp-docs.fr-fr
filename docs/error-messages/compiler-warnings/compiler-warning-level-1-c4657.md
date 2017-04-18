---
title: Compilateur avertissement (niveau 1) C4657 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4657
dev_langs:
- C++
helpviewer_keywords:
- C4657
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 2ac407b6e2ed17eb7a9c1f1232756e9977ed7511
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4657"></a>Avertissement du compilateur (niveau 1) C4657
l’expression implique un type de données postérieur à la dernière génération  
  
 Vous avez ajouté ou modifié un type de données, ce qui le rend nouveau pour votre code source depuis la dernière génération réussie. Modifier & Continuer ne prend pas en charge les modifications sur les types de données existants.  
  
 Cet avertissement sera toujours suivi [erreur irrécupérable C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Pour plus d’informations, consultez la [prise en charge des modifications de Code](/visualstudio/debugger/supported-code-changes-cpp).  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Pour supprimer cet avertissement sans mettre fin à la session de débogage en cours  
  
1.  Replacez le type de données dans l’état où il se trouvait avant l’erreur.  
  
2.  Dans le menu **Déboguer** , choisissez **Appliquer les modifications du code**.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>Pour supprimer cette erreur sans modifier votre code source  
  
1.  Dans le menu **Déboguer** , choisissez **Arrêter le débogage**.  
  
2.  Dans le menu **Générer** , cliquez sur **Générer**.
