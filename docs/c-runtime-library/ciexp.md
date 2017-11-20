---
title: _CIexp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CIexp
apilocation:
- msvcr120.dll
- msvcr80.dll
- msvcr110.dll
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- CIexp
- _CIexp
dev_langs: C++
helpviewer_keywords:
- CIexp intrinsic
- _CIexp intrinsic
ms.assetid: f8a3e3b7-fa57-41a3-9983-6c81914cbb55
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2dba94eabd7505e9e8e4340e933a08736222b461
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ciexp"></a>_CIexp
Calcule la valeur exponentielle de la valeur supérieure de la pile.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __cdecl _CIexp();  
```  
  
## <a name="remarks"></a>Notes  
 Cette version de la fonction `exp` a une convention d’appel spécialisée que le compilateur comprend. Elle accélère l’exécution, car elle empêche la génération de copies et facilite l’allocation de registres.  
  
 La valeur obtenue est placée en haut de la pile.  
  
## <a name="requirements"></a>Spécifications  
 **Plateforme :** x86  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp, expf, expl](../c-runtime-library/reference/exp-expf.md)