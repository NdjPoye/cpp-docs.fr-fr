---
title: "Avertissement des outils &#201;diteur de liens LNK4006 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4006"
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbole déjà défini dans objet ; seconde définition ignorée  
  
 Le `symbol` donné, affiché sous forme décorée, a été défini plusieurs fois.  Quand cet avertissement apparaît, `symbol` est ajouté deux fois, mais seule sa première forme est utilisée.  
  
 Vous pouvez obtenir cet avertissement si vous tentez de fusionner deux bibliothèques d'importation en une seule.  
  
 Si vous régénérez la bibliothèque runtime C, vous pouvez ignorer ce message.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Le `symbol` donné peut être une fonction packagée, créée par compilation avec [\/Gy](../../build/reference/gy-enable-function-level-linking.md).  Ce symbole a été inclus dans plus d'un fichier mais a été modifié entre les compilations.  Recompilez tous les fichiers qui incluent le `symbol`.  
  
2.  Le `symbol` donné peut avoir été défini de façon différente dans deux objets membres de bibliothèques différentes.  
  
3.  Un absolu peut avoir été défini deux fois, avec une valeur différente dans chaque définition.  
  
4.  Si le message d'erreur apparaît lors de la combinaison de bibliothèques, `symbol` existe déjà dans la bibliothèque ajoutée.