---
title: Erreur ML non fatale A2133 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2133
dev_langs: C++
helpviewer_keywords: A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 343c2fae3d3c1fe97224e8fac990b29786e50cdf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ml-nonfatal-error-a2133"></a>Erreur ML non fatale A2133
**remplacé par INVOKE de valeur de Registre**  
  
 Un Registre a été passé comme argument à une procédure, mais le code généré par [INVOKE](../../assembler/masm/invoke.md) pour passer des autres arguments détruit le contenu du Registre.  
  
 Les registres AX, AL, AH, EAX, DX, DL, Diffie-Hellman et EDX peuvent être utilisés par l’assembleur pour effectuer la conversion de données.  
  
 Utilisez un autre registre.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)