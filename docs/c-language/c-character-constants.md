---
title: "Constantes caractère C | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- characters, constants
- (') single quotation mark
- constants, character
- single quotation mark
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 374870a385e12d301731c0f9232d09895d8906c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c-character-constants"></a>Constantes caractère C
Une constante caractère est formée en plaçant un caractère du jeu de caractères représentable entre guillemets simples (**' '**). Les constantes caractère sont utilisées pour représenter des caractères dans le [jeu de caractères d'exécution](../c-language/execution-character-set.md).  
  
## <a name="syntax"></a>Syntaxe  
 *character-constant* :  
 **'** *c-char-sequence* **'**  
  
 **L'** *c-char-sequence* **'**  
  
 *c-char-sequence* :  
 *c-char*  
  
 *c-char-sequence c-char*  
  
 *c-char* :  
 Tout membre du jeu de caractères source à l'exception du guillemet simple (**'**), de la barre oblique inverse (**\\**) ou du caractère de saut de ligne  
  
 *escape-sequence*  
  
 *escape-sequence* :  
 *simple-escape-sequence*  
  
 *octal-escape-sequence*  
  
 *hexadecimal-escape-sequence*  
  
 *simple-escape-sequence* : un des éléments suivants :  
 **\a \b \f \n \r \t \v**  
  
 **\\' \\" \\\ \\?**  
  
 *octal-escape-sequence* :  
 **\\**  *octal-digit*  
  
 **\\**  *octal-digit octal-digit*  
  
 **\\**  *octal-digit octal-digit octal-digit*  
  
 *hexadecimal-escape-sequence* :  
 **\x**  *hexadecimal-digit*  
  
 *hexadecimal-escape-sequence hexadecimal-digit*  
  
## <a name="see-also"></a>Voir aussi  
 [Constantes C](../c-language/c-constants.md)