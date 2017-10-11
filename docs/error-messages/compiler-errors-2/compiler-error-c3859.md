---
title: Erreur du compilateur C3859 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3859
dev_langs:
- C++
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8a132eb7dbf09421ad5c99249b0208e5f901156b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3859"></a>Erreur du compilateur C3859
plage de mémoire virtuelle dépassée pour PCH ; recompilez avec une option de ligne de commande ’-Zmvalue’ ou supérieur  
  
 Votre en-tête précompilé est trop petit pour la quantité de données que le compilateur tente d’y placer. Utilisez le **/Zm** indicateur de compilateur pour spécifier une valeur supérieure pour le fichier d’en-tête précompilé. Pour plus d’informations, consultez [/Zm (spécifier précompilés en-tête limite d’Allocation mémoire)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).
