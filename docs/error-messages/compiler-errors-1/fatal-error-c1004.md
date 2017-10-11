---
title: "Erreur irrécupérable C1004 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c6a9e74d7918e1cb2c9190c87f4f1ec75f89237b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1004"></a>Erreur irrécupérable C1004
fin de fichier inattendue rencontrée  
  
 Le compilateur a atteint la fin d’un fichier source sans pouvoir résoudre une construction. Le code peut être manquant, un des éléments suivants :  
  
-   Une accolade fermante  
  
-   Une parenthèse fermante  
  
-   Marque de commentaire fermant (* /)  
  
-   Un point-virgule  
  
 Pour résoudre cette erreur, vérifiez les éléments suivants :  
  
-   Le lecteur de disque par défaut l’espace est insuffisant pour les fichiers temporaires, lesquels nécessitent environ deux fois plus d’espace que le fichier source.  
  
-   Un `#if` directive qui correspond à false manque une fermeture `#endif` directive.  
  
-   Un fichier source ne se termine pas par un retour chariot et un saut de ligne.  
  
 L’exemple suivant génère l’erreur C1004 :  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 Résolution possible :  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```
