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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 71f2bf8ef42896447d48c9cb3581006c2e3d7620
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1352"></a>Erreur irrécupérable C1352
Code MSIL non valide ou endommagé dans la fonction 'fonction' à partir de 'fichier' de module  
  
 Un fichier .netmodule a été passé au compilateur, mais le compilateur a détecté que le fichier était endommagé.  Demandez à l’auteur du fichier .netmodule de rechercher l’origine du problème.  
  
 Le compilateur ne recherche pas tous les types d’endommagements dans les fichiers .netmodule qu’il vérifie.  Toutefois, il vérifie que tous les chemins de contrôle d’une fonction contiennent bien une instruction return.  
  
 Pour plus d’informations, consultez [Fichiers .netmodule en tant qu’entrée de l’Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md).
