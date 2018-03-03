---
title: "Erreur irrécupérable NMAKE U1033 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94f2626e1ce318d83d306595e386f880c62dec3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1033"></a>Erreur irrécupérable NMAKE U1033
Erreur de syntaxe : 'chaîne' inattendu  
  
 La chaîne n’est pas partie de la syntaxe valide d’un makefile.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Si la valeur de la fermeture de crochets pointus (**<<**) pour un fichier inline ne sont pas au début d’une ligne, l’erreur suivante se produit :  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  Si une définition de macro dans le makefile contenue un signe égal (**=**) sans précédente nom ou si le nom en cours est une macro qui se développe vers rien, l’erreur suivante se produit :  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  Si le point-virgule (**;**) dans une ligne de commentaire dans les outils. INI n’est pas au début de la ligne, l’erreur suivante se produit :  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  Si le makefile a été mis en forme par un traitement de texte, l’erreur suivante peut se produire :  
  
    ```  
    syntax error : ':' unexpected  
    ```