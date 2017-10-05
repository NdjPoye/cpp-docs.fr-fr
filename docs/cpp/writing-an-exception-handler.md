---
title: "L’écriture d’un gestionnaire d’exceptions | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling, exception handlers
- exception handling, exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
caps.latest.revision: 7
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5f3f81ff6ea954cda7270ff32650d5744280d918
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="writing-an-exception-handler"></a>Écriture d'un gestionnaire d'exceptions
Les gestionnaires d'exceptions sont généralement utilisés pour répondre à des erreurs spécifiques. Vous pouvez utiliser la syntaxe de gestion des exceptions pour filtrer les exceptions autres que celles que vous savez gérer. D'autres exceptions doivent être passées à d'autres gestionnaires (éventuellement dans la bibliothèque Runtime ou dans le système d'exploitation) écrits pour rechercher ces exceptions spécifiques.  
  
 Les gestionnaires d'exceptions utilisent l'instruction try-except.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
  
-   [Try-except, instruction](../cpp/try-except-statement.md)  
  
-   [Écriture d’un filtre d’exception](../cpp/writing-an-exception-filter.md)  
  
-   [Le déclenchement d’exceptions logicielles](../cpp/raising-software-exceptions.md)  
  
-   [Exceptions matérielles](../cpp/hardware-exceptions.md)  
  
-   [Restrictions sur les gestionnaires d’exceptions](../cpp/restrictions-on-exception-handlers.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
