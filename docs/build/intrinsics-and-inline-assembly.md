---
title: "Fonctions intrinsèques et Inline Assembly | Documents Microsoft"
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
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80eb16eb7fde49c499227bb3d60000e2ac6e5143
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="intrinsics-and-inline-assembly"></a>Assembly de fonctions intrinsèques et inline
Une des contraintes pour le [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] compilateur consiste à n’avoir aucune prise en charge d’assembleur inline. Cela signifie que les fonctions qui ne peut pas être écrit en C ou C++ doivent être écrites en tant que sous-routines ou des fonctions intrinsèques prises en charge par le compilateur. Certaines fonctions sont sensibles aux performances et d’autres non. Les fonctions sensibles aux performances doivent être implémentées comme fonctions intrinsèques.  
  
 Les fonctions intrinsèques prises en charge par le compilateur sont décrites dans [intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Conventions des logiciels x64](../build/x64-software-conventions.md)