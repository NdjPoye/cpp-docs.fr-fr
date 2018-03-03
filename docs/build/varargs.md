---
title: Varargs | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3d22a5c3f20480d1e904ec8e087114385ba7ee9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="varargs"></a>Varargs
Si des paramètres sont passés via varargs (par exemple, les arguments de points de suspension), essentiellement le passage de paramètres normal s’applique notamment déversement les arguments de la cinquième et ultérieures. Il incombe à nouveau l’appelé aux arguments de vidage qui ont leur adresse. Pour les valeurs à virgule flottante, l’entier et le Registre à virgule flottante contiendra la valeur float si l’appelé attend la valeur dans les registres d’entiers.  
  
## <a name="see-also"></a>Voir aussi  
 [Convention d’appel](../build/calling-convention.md)