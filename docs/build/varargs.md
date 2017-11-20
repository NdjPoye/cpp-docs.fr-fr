---
title: Varargs | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8492610721846e8252cbe71b358e428a2aaf024f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="varargs"></a>Varargs
Si des paramètres sont passés via varargs (par exemple, les arguments de points de suspension), essentiellement le passage de paramètres normal s’applique notamment déversement les arguments de la cinquième et ultérieures. Il incombe à nouveau l’appelé aux arguments de vidage qui ont leur adresse. Pour les valeurs à virgule flottante, l’entier et le Registre à virgule flottante contiendra la valeur float si l’appelé attend la valeur dans les registres d’entiers.  
  
## <a name="see-also"></a>Voir aussi  
 [Convention d’appel](../build/calling-convention.md)