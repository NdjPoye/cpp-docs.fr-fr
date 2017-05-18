---
title: "Erreur irrécupérable C1352 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1352
dev_langs:
- C++
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 66584dc786a3340deeaf1176362bf64dafacd3b8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1352"></a>Erreur irrécupérable C1352
Code MSIL non valide ou endommagé dans la fonction 'fonction' à partir de 'fichier' de module  
  
 Un fichier .netmodule a été passé au compilateur, mais le compilateur a détecté que le fichier était endommagé.  Demandez à l’auteur du fichier .netmodule de rechercher l’origine du problème.  
  
 Le compilateur ne recherche pas tous les types d’endommagements dans les fichiers .netmodule qu’il vérifie.  Toutefois, il vérifie que tous les chemins de contrôle d’une fonction contiennent bien une instruction return.  
  
 Pour plus d’informations, consultez [fichiers .netmodule en tant qu’entrée de l’éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md).
