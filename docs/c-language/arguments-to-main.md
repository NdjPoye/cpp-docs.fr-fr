---
title: "Arguments de main | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 39824fef-05ad-461d-ae82-49447dda8060
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Arguments de main
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 2.1.2.2.1** La sémantique des arguments de main  
  
 Dans Microsoft C, la fonction appelée au démarrage du programme est appelée **main**.  Il n'existe aucun prototype déclaré pour **main** et cette fonction peut être définie avec zéro, deux ou trois paramètres :  
  
```  
int main( void )  
int main( int argc, char *argv[] )  
int main( int argc, char *argv[], char *envp[] )  
```  
  
 La troisième ligne ci\-dessus, où **main** accepte trois paramètres, est une extension Microsoft de la norme C ANSI.  Le troisième paramètre, **envp**, est un tableau de pointeurs vers des variables d'environnement.  Le tableau **envp** est arrêté par un pointeur null.  Consultez [La fonction main et l'exécution du programme](../c-language/main-function-and-program-execution.md) pour plus d'informations sur **main** et **envp**.  
  
 La variable **argc** ne contient jamais de valeur négative.  
  
 Le tableau de chaînes se termine par **argv\[argc\]**, qui contient un pointeur null.  
  
 Tous les éléments du tableau **argv** sont des pointeurs vers des chaînes.  
  
 Un programme appelé sans argument de ligne de commande reçoit une valeur de un pour **argc** lorsque le nom du fichier exécutable est placé dans **argv\[0\]**. Dans les versions MS\-DOS antérieures à 3.0, le nom du fichier exécutable n'est pas disponible.  La lettre C est placée dans **argv\[0\]**. Les chaînes pointées par **argv\[1\]** à **argv\[argc – 1\]** représentent des paramètres de programme.  
  
 Les paramètres **argc** et **argv** sont modifiables et conservent leurs dernières valeurs stockées entre le démarrage du programme et l'arrêt du programme.  
  
## Voir aussi  
 [Environnement](../c-language/environment.md)