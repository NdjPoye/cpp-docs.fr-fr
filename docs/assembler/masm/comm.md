---
title: COMM | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COMM
dev_langs: C++
helpviewer_keywords: COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad12de948227f98ec73f779030b8e644dfad8b2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comm"></a>COMM
Crée une variable communes avec les attributs spécifiés dans `definition`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>Notes  
 Chaque `definition` a la forme suivante :  
  
 [[*langtype*]] [[**NEAR** &#124; **FAR**]] *étiquette***:**`type`[[**:***nombre*]]  
  
 Le *étiquette* est le nom de la variable. Le `type` peut être n’importe quel spécificateur de type ([octets](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md), et ainsi de suite) ou un entier spécifiant le nombre d’octets. Le *nombre* Spécifie le nombre d’objets de données (une est la valeur par défaut).  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)