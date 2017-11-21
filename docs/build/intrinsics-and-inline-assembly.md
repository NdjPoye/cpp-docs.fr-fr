---
title: "Fonctions intrinsèques et Inline Assembly | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c60932b719b25365c7d8f65a4649ef782a4f9888
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="intrinsics-and-inline-assembly"></a>Assembly de fonctions intrinsèques et inline
Une des contraintes pour le [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] compilateur consiste à n’avoir aucune prise en charge d’assembleur inline. Cela signifie que les fonctions qui ne peut pas être écrit en C ou C++ doivent être écrites en tant que sous-routines ou des fonctions intrinsèques prises en charge par le compilateur. Certaines fonctions sont sensibles aux performances et d’autres non. Les fonctions sensibles aux performances doivent être implémentées comme fonctions intrinsèques.  
  
 Les fonctions intrinsèques prises en charge par le compilateur sont décrites dans [intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Conventions des logiciels x64](../build/x64-software-conventions.md)