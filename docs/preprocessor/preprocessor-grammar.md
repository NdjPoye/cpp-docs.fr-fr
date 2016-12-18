---
title: "Grammaire du pr&#233;processeur | Microsoft Docs"
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
helpviewer_keywords: 
  - "grammaire, préprocesseur"
  - "préprocesseur"
  - "préprocesseur, grammaire"
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Grammaire du pr&#233;processeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\#define**  *identifier* *token\-string*opt  
  
 *\#* **define**  *identifier*\[**\(** *identifier*opt**,** *...* **,** *identifier*opt **\)**\] *token\-string*opt  
  
 **defined\(**  *identifier* **\)**  
  
 **defined**  *identifier*  
  
 `#include` **"***path\-spec***"**  
  
 `#include` **\<***path\-spec***\>**  
  
 **\#line**  *digit\-sequence*  **"** *filename* **"** opt  
  
 *\#* **undef**  *identifier*  
  
 **\#error**  *token\-string*  
  
 **\#pragma**  *token\-string*  
  
 *conditional*  :  
 *if\-part elif\-parts* opt *else\-part*opt *endif\-line*  
  
 *if\-part*  :  
 *if\-linetext*  
  
 *if\-line*  :  
 **\#if**  *constant\-expression*  
  
 **\#ifdef**  *identifier*  
  
 **\#ifndef**  *identifier*  
  
 *elif\-parts*  :  
 *elif\-line text*  
  
 *elif\-parts elif\-line text*  
  
 *elif\-line*  :  
 **\#elif**  *constant\-expression*  
  
 *else\-part*  :  
 *else\-linetext*  
  
 *else\-line*  :  
 `#else`  
  
 *endif\-line*  :  
 `#endif`  
  
 *digit\-sequence*  :  
 *digit*  
  
 *digit\-sequence digit*  
  
 *digit*  : un des éléments suivants :  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *token\-string*  :  
 Chaîne de jetons  
  
 *token*  :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *filename*  :  
 Nom de fichier du système d'exploitation conforme  
  
 *path\-spec*  :  
 Chemin d'accès de fichier conforme  
  
 *text* :  
 Toute séquence de texte  
  
> [!NOTE]
>  Les éléments non terminaux suivants sont développés dans l'Annexe A, [Résumé de la grammaire](../misc/grammar-summary-cpp.md), *du Guide de référence du langage C\+\+* : `constant`, `constant`\-*expression*, *identifier*, *keyword*, `operator` et `punctuator`.  
  
## Voir aussi  
 [Résumé de la grammaire](../preprocessor/grammar-summary-c-cpp.md)