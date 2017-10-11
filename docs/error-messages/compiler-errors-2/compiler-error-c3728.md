---
title: Erreur du compilateur C3728 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3728
dev_langs:
- C++
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 100ef8275f938406a4f6a7d3909e04f40ce1d16b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3728"></a>Erreur du compilateur C3728
'événement' : événement n’a pas de méthode raise  
  
 Les métadonnées créées avec un langage tel que c#, qui n’autorise pas un événement est déclenché à partir d’à l’extérieur de la classe dans laquelle il a été défini, ont été inclus avec le [#using](../../preprocessor/hash-using-directive-cpp.md) directive et un programme Visual C++ à l’aide de la programmation CLR essaie déclenche l’événement.  
  
 Pour déclencher un événement dans un programme développé dans un langage comme c#, la classe contenant l’événement doit également définir une méthode publique qui déclenche l’événement.
