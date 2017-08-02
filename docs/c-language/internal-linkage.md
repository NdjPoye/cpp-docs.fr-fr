---
title: Liaison interne | Microsoft Docs
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
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
caps.latest.revision: 6
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
ms.openlocfilehash: 6d693f4d12fcfe048ef16d9eb8e8806a58d62030
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="internal-linkage"></a>Liaison interne
Si la déclaration d'un identificateur de portée de fichier pour un objet ou une fonction contient le *storage-class-specifier* **static**, l'identificateur a une liaison interne. Sinon, l'identificateur a une liaison externe. Consultez [Classes de stockage](../c-language/c-storage-classes.md) pour plus d'informations sur l'élément non terminal *storage-class-specifier*.  
  
 Dans une unité de traduction, chaque instance d'un identificateur avec une liaison interne désigne le même identificateur ou la même fonction. Les identificateurs liés en interne sont spécifiques à une unité de traduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation d’extern pour spécifier la liaison](../cpp/using-extern-to-specify-linkage.md)
