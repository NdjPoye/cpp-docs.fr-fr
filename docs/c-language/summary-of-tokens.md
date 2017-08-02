---
title: "Résumé des jetons | Microsoft Docs"
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
ms.assetid: 2978cbf6-e66e-46fc-9938-caa052f2ccf7
caps.latest.revision: 8
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
ms.openlocfilehash: bf77442b8bc06b2f862497a2ce8d8d522cff3b6b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="summary-of-tokens"></a>Résumé des jetons
*token* :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *string-literal*  
  
 *operator*  
  
 `punctuator`  
  
 *preprocessing-token* :  
 *header-name*  
  
 *identifier*  
  
 *pp-number*  
  
 *character-constant*  
  
 *string-literal*  
  
 *operator punctuator*  
  
 chaque caractère autre qu'un espace blanc qui ne peut pas être l'un des éléments ci-dessus  
  
 *header-name* :  
 **\<**  *path-spec*  **> "**  *path spec*  **"**  
  
 *path-spec* :  
 Chemin d’accès de fichier conforme  
  
 *pp-number* :  
 *digit*  
  
 **.** *digit*  
  
 *pp-number digit*  
  
 *pp-number nondigit*  
  
 *pp-number*  **e**  *sign*  
  
 *pp-number*  **E**  *sign*  
  
 *pp-number*  **.**  
  
## <a name="see-also"></a>Voir aussi  
 [Grammaire lexicale](../c-language/lexical-grammar.md)
