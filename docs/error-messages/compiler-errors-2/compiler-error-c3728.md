---
title: Erreur du compilateur C3728 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3728
dev_langs: C++
helpviewer_keywords: C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d20a0772a38dadc5956e1d174a23ecb0a8593647
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3728"></a>Erreur du compilateur C3728
'événement' : événement n’a pas de méthode raise  
  
 Les métadonnées créées avec un langage tel que c#, qui n’autorise pas un événement est déclenché à partir d’à l’extérieur de la classe dans laquelle il a été défini, ont été inclus avec le [#using](../../preprocessor/hash-using-directive-cpp.md) directive et un programme Visual C++ à l’aide de la programmation CLR essaie déclenche l’événement.  
  
 Pour déclencher un événement dans un programme développé dans un langage comme c#, la classe contenant l’événement doit également définir une méthode publique qui déclenche l’événement.