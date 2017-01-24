---
title: "Erreur irr&#233;cup&#233;rable C1071 | Microsoft Docs"
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
  - "C1071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1071"
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fin de fichier inattendue dans un commentaire  
  
 Le compilateur a atteint la fin du fichier pendant le parcours d'un commentaire.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Terminaison de commentaire manquante \(\*\/\).  
  
2.  Caractères de saut de ligne manquants après un commentaire sur la dernière ligne d'un fichier source.  
  
 L'exemple suivant génère l'erreur C1071 :  
  
```  
// C1071.cpp  
int main() {  
}  
  
/* this comment is fine */  
/* forgot the closing tag        // C1071  
```