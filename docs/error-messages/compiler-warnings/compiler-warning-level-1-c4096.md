---
title: "L’erreur C4096 (niveau 1) d’avertissement de compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4096
dev_langs: C++
helpviewer_keywords: C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3c8fd8e18743a4cf0c9004236ab60bb30219119e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4096"></a>Erreur C4096 de compilateur (niveau 1) d’avertissement
« a » : interface n’est pas une interface COM ; ne sera pas émise vers IDL  
  
 Une définition d’interface prévu comme une interface COM n’a pas été définie comme une interface COM et ne sera donc pas émise dans le fichier IDL.  
  
 Consultez [des attributs d’Interface](../../windows/interface-attributes.md) pour une liste d’attributs indiquant qu’une interface est une interface COM.  
  
 L’exemple suivant génère l’erreur C4096 :  
  
```  
// C4096.cpp  
// compile with: /W1 /LD  
#include "windows.h"  
[module(name="xx")];  
  
// [object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct b : a  
{  
};   // C4096, remove coclass or uncomment object  
```