---
title: "Erreur irrécupérable C1092 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 6d93fd662b638126e21d5f5f034138c0e6f0e0ad
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1092"></a>Erreur irrécupérable C1092
Modifier & Continuer ne prend pas en charge les modifications sur les types de données ; génération requise  
  
 Vous avez modifié ou ajouté un type de données depuis la dernière génération réussie.  
  
-   Modifier & Continuer ne prend pas en charge les modifications apportées aux types de données existants, notamment des définitions de classe, struct ou enum. Vous devez arrêter le débogage et générez l’application.  
  
-   Modifier & Continuer ne prend pas en charge l’ajout de nouveaux types de données si un fichier de base de données de programme, tel que vc*x*0.pdb (où *x* est la version principale de Visual C++ utilisé) est en lecture seule. Pour ajouter des types de données, le compilateur doit ouvrir le fichier .pdb en mode écriture.  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Pour supprimer cette erreur sans mettre fin à la session de débogage en cours  
  
1.  Replacez le type de données dans l’état où il se trouvait avant l’erreur.  
  
2.  Dans le menu **Déboguer** , choisissez **Appliquer les modifications du code**.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>Pour supprimer cette erreur sans modifier votre code source  
  
1.  Dans le menu **Déboguer** , choisissez **Arrêter le débogage**.  
  
2.  Dans le menu **Générer** , cliquez sur **Générer**.  
  
 Pour plus d’informations, consultez la [prise en charge des modifications de Code](/visualstudio/debugger/supported-code-changes-cpp).
