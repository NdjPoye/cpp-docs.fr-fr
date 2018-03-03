---
title: Compilateur avertissement (niveau 3) C4192 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 022c0e0aac8d231963ddf6d5d3715d55f726a8b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4192"></a>Compilateur avertissement (niveau 3) C4192
exclusion automatique de 'name' lors de l’importation de bibliothèque de types 'library'  
  
 A `#import` bibliothèque contient un élément, *nom*, qui est également défini dans les en-têtes systèmes Win32. En raison des limitations des bibliothèques de types, des noms tels que **IUnknown** ou GUID sont souvent définis dans une bibliothèque de types, dupliquant la définition provenant des en-têtes système. `#import`détectera ces éléments et refuser les incorporer dans les fichiers d’en-tête .tlh et .tli.  
  
 Pour remplacer ce comportement, utilisez `#import` attributs [no_auto_exclude](../../preprocessor/no-auto-exclude.md) et [include()](../../preprocessor/include-parens.md).