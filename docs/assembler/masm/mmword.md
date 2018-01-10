---
title: MMWORD | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MMWORD
dev_langs: C++
helpviewer_keywords: MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbe20f842a97186071431cd73e7de65fa8170bd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mmword"></a>MMWORD
Utilisé pour les opérandes de multimédias 64 bits avec des instructions MMX et SSE (XMM).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
MMWORD  
```  
  
## <a name="remarks"></a>Notes  
 `MMWORD`est un type.  Avant de MMWORD ajouté à MASM, une fonctionnalité équivalente pourrait avoir été obtenue avec :  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 Alors que les deux instructions fonctionnent sur les opérandes de 64 bits, `QWORD` est de type pour les entiers non signés 64 bits et `MMWORD` est le type de valeur multimédia 64 bits.  
  
 `MMWORD`est destiné à représenter le même type que [__m64](../../cpp/m64.md).  
  
## <a name="example"></a>Exemple  
  
```  
movq     mm0, mmword ptr [ebx]  
```