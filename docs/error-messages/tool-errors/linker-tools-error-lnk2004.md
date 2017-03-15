---
title: "Erreur des outils &#201;diteur de liens LNK2004 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2004"
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur des outils &#201;diteur de liens LNK2004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

dépassement de la correction gp relative à 'cible' ; la section short 'section' est trop grande ou hors limites.  
  
 La section était trop grande.  
  
 Pour résoudre cette erreur, réduisez la taille de la section short, soit en insérant explicitement des données dans les sections long via \#pragma section\(".NomSection", read, write, long\) et en utilisant `__declspec(allocate(".sectionname"))` sur les définitions de données et les déclarations.  Par exemple :  
  
```  
#pragma section(".data$mylong", read, write, long)  
__declspec(allocate(".data$mylong"))  
char    rg0[1] = { 1 };  
char    rg1[2] = { 1 };  
char    rg2[4] = { 1 };  
char    rg3[8] = { 1 };  
char    rg4[16] = { 1 };  
char    rg5[32] = { 1 };  
```  
  
 Vous pouvez également déplacer des données groupées de manière logique dans leur propre structure qui sera une collection de données supérieure à 8 octets allouée ensuite par le compilateur dans une section de données long.  Par exemple :  
  
```  
// from this...  
int     w1  = 23;  
int     w2 = 46;  
int     w3 = 23*3;  
int     w4 = 23*4;  
  
// to this...  
struct X {  
    int     w1;  
    int     w2;  
    int     w3;  
    int     w4;  
} x  = { 23, 23*2, 23*3, 23*4 };  
  
```  
  
 Ce message d'erreur est suivi de l'erreur irrécupérable `LNK1165`.