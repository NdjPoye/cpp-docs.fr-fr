---
title: "Résumé des instructions | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a8fbebed0608ba21973fdc93d2812b497ca3dc83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="summary-of-statements"></a>Résumé des instructions
*instruction* :  
 *labeled-statement*  
  
 *compound-statement*  
  
 *expression-statement*  
  
 *selection-statement*  
  
 *iteration-statement*  
  
 *jump-statement*  
  
 *try-except-statement* /* Spécifique de Microsoft \*/  
  
 *try-finally-statement* /* Spécifique de Microsoft \*/  
  
 *saut-instruction* :  
 **goto**  *identifier*  **;**  
  
 **continue ;**  
  
 **break ;**  
  
 **return**  *expression*opt**;**  
  
 *compound-statement*:  
 **{**  *declaration-list*opt*statement-list*opt**}**  
  
 *declaration-list* :  
 *déclaration*  
  
 *declaration-list declaration*  
  
 *statement-list*:  
 *statement*  
  
 *statement-list statement*  
  
 *expression-statement*:  
 *expression*opt**;**  
  
 *itération-instruction* :  
 **while (**  *expression*  **)**  *statement*  
  
 **do**  *statement*  **while (**  *expression*  **) ;**  
  
 **for (**  *expression*opt**;** *expression*opt**;** *expression*opt**)** *statement*  
  
 *selection-statement* :  
 **if (**  *expression*  **)**  *statement*  
  
 **if (**  *expression*  **)**  *statement*  **else**  *statement*  
  
 **switch (** *expression* **)** *statement*  
  
 *labeled-statement* :  
 *identificateur*  **:**  *instruction*  
  
 **case**  *constant-expression*  **:**  *statement*  
  
 **default :**  *statement*  
  
 *try-except-statement*:   /\* Spécifique de Microsoft  \*/  
 **__try**  *compound-statement*  
  
 **__except (**  *expression*  **)**  *compound-statement*  
  
 *try-finally-statement*:   /\* Spécifique de Microsoft \*/  
 **__try**  *compound-statement*  
  
 **__finally**  *compound-statement*  
  
## <a name="see-also"></a>Voir aussi  
 [Grammaire de la structure de la phrase](../c-language/phrase-structure-grammar.md)