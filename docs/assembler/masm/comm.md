---
title: COMM | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 111dac47089fea13febe787e5b73557b287beea8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="comm"></a>COMM
Crée une variable communes avec les attributs spécifiés dans `definition`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>Notes  
 Chaque `definition` a la forme suivante :  
  
 [[*langtype*]] [[**NEAR** &#124; **FAR**]] *étiquette ***:**`type`[[**:*** nombre*]]  
  
 Le *étiquette* est le nom de la variable. Le `type` peut être n’importe quel spécificateur de type ([octets](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md), et ainsi de suite) ou un entier spécifiant le nombre d’octets. Le *nombre* Spécifie le nombre d’objets de données (une est la valeur par défaut).  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)