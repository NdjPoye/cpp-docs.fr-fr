---
title: "Erreur irr&#233;cup&#233;rable C1004 | Microsoft Docs"
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
  - "C1004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1004"
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fin de fichier inattendue rencontrée  
  
 Le compilateur a atteint la fin d'un fichier source sans pouvoir résoudre une construction.  Il peut manquer un des éléments suivants dans le code :  
  
-   une accolade fermante ;  
  
-   une parenthèse fermante ;  
  
-   un délimiteur fermant de commentaire \(\*\/\)  
  
-   un point\-virgule.  
  
 Pour corriger cette erreur, vérifiez les points suivants :  
  
-   Le lecteur de disque par défaut n'a pas suffisamment de place pour les fichiers temporaires, qui prennent environ deux fois plus de place que le fichier source.  
  
-   Une directive `#if` qui correspond à la valeur false n'a pas de directive fermante `#endif` correspondante.  
  
-   Un fichier source ne se termine pas par un retour chariot et un changement de ligne.  
  
 L'exemple suivant génère l'erreur C1004 :  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 Résolution possible :  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```