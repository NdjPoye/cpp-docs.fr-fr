---
title: Naked (C) | Microsoft Docs
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
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
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
ms.openlocfilehash: 24266f2241ddb60d4a5403447a87caaa08ddaf08
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="naked-c"></a>Naked (C)
**Section spécifique à Microsoft**  
  
 L’attribut de classe de stockage naked est une extension spécifique à Microsoft pour le langage C. Le compilateur génère un code sans code de prologue ni d'épilogue pour les fonctions déclarées avec l'attribut de classe de stockage naked. Les fonctions naked sont utiles lorsque vous devez écrire vos propres séquences de code de prologue/épilogue à l'aide de code assembleur inline. Les fonctions naked sont utiles pour écrire des pilotes de périphériques virtuels.  
  
 Pour obtenir des informations spécifiques sur l'utilisation de l'attribut naked, consultez [Fonctions naked](../c-language/naked-functions.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs étendus de classe de stockage C](../c-language/c-extended-storage-class-attributes.md)