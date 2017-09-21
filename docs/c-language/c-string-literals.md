---
title: "Littéraux de chaîne C | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 2ca39273bff41d1a08d078445ddf8d8b56252db8
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="c-string-literals"></a>Littéraux de chaîne C
Un littéral de chaîne est une séquence de caractères du jeu de caractères source placée entre guillemets (**" "**). Les littéraux de chaîne servent à représenter une séquence de caractères qui, une fois combinés, forment une chaîne terminée par le caractère Null. Vous devez toujours faire précéder les littéraux de chaîne étendue de la lettre **L**.  
  
## <a name="syntax"></a>Syntaxe  
 *string-literal*:  
 **"** *s-char-sequence* opt**"**  
  
 **L"** *s-char-sequence* opt**"**  
  
 *s-char-sequence*:  
 *s-char*  
  
 *s-char-sequence s-char*  
  
 *s-char* :  
 Tout membre du jeu de caractères source à l'exception du guillemet double ("), de la barre oblique inverse (\\) ou du caractère de saut de ligne  
  
 *escape-sequence*  
  
 L'exemple ci-dessous est un littéral de chaîne simple :  
  
```  
char *amessage = "This is a string literal.";  
```  
  
 Tous les codes d'échappement répertoriés dans le tableau [Séquences d’échappement](../c-language/escape-sequences.md) sont valides dans les littéraux de chaîne. Pour représenter un guillemet double dans un littéral de chaîne, utilisez la séquence d'échappement **\\"**. Le guillemet simple (**'**) peut être représenté sans séquence d'échappement. La barre oblique inverse (**\\**) doit être suivie d'une seconde barre oblique inverse (**\\\\**) lorsqu'elle apparaît dans une chaîne. Lorsqu'une barre oblique inverse apparaît à la fin d'une ligne, elle est toujours interprétée comme un caractère de continuation de ligne.  
  
## <a name="see-also"></a>Voir aussi  
 [Éléments de C](../c-language/elements-of-c.md)