---
title: Compilateur avertissement (niveau 1) C4420 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4420
dev_langs: C++
helpviewer_keywords: C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9a57803cb584f5ee54ad5533366e6aadc85d1acf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4420"></a>Avertissement du compilateur (niveau 1) C4420
'opérateur' : opérateur non disponible, à l’aide de 'opérateur' à la place. vérification de l’exécution peut être compromise.  
  
 Cet avertissement est généré lorsque vous utilisez la [que /RTCv](../../build/reference/rtc-run-time-error-checks.md) (nouveau/supprimer la vérification de vecteur) et qu’aucune forme vecteur n’est trouvée. Dans ce cas, c’est la forme non vecteur qui est utilisée.  
  
 Dans l’ordre pour que /RTCv fonctionne correctement, le compilateur doit toujours appeler la forme vecteur de [nouveau](../../cpp/new-operator-cpp.md)/[supprimer](../../cpp/delete-operator-cpp.md) si la syntaxe vecteur a été utilisée.