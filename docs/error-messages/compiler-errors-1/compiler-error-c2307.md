---
title: Erreur du compilateur C2307 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2307
dev_langs:
- C++
helpviewer_keywords:
- C2307
ms.assetid: ce6c8033-a673-4679-9883-bedec36ae385
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 13658dd4c9430bd6e3cda53af741659264619994
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2307"></a>Erreur du compilateur C2307
pragma 'pragma' doit être une fonction externe si la compilation incrémentielle est activée  
  
 Vous devez placer le `data_seg` pragma entre les fonctions si vous utilisez la compilation incrémentielle.
