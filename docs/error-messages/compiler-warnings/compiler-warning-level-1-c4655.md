---
title: Compilateur avertissement (niveau 1) C4655 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4655
dev_langs:
- C++
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
caps.latest.revision: 6
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
ms.openlocfilehash: 058086bb4617f59f53de706b38477bd868e297d3
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4655"></a>Avertissement du compilateur (niveau 1) C4655
**'**   
 ***symbole* ' : variable type depuis la dernière génération, ou défini différemment ailleurs.**  
  
 Vous avez modifié ou ajouté un nouveau type de données depuis la dernière génération réussie. Modifier & Continuer ne prend pas en charge les modifications sur les types de données existants.  
  
 Cet avertissement est suivi par un [erreur irrécupérable C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Pour plus d’informations, consultez la [prise en charge des modifications de Code](/visualstudio/debugger/supported-code-changes-cpp).  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Pour supprimer cet avertissement sans mettre fin à la session de débogage en cours  
  
1.  Replacez le type de données dans l’état où il se trouvait avant l’erreur.  
  
2.  Dans le menu **Déboguer** , choisissez **Appliquer les modifications du code**.  
  
### <a name="to-remove-this-warning-without-changing-your-source-code"></a>Pour supprimer cette erreur sans modifier votre code source  
  
1.  Dans le menu **Déboguer** , choisissez **Arrêter le débogage**.  
  
2.  Dans le menu **Générer** , cliquez sur **Générer**.
