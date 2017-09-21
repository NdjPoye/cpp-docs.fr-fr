---
title: __CxxFrameHandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __CxxFrameHandler
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __CxxFrameHandler
dev_langs:
- C++
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 9798d46172aac730abaebe8ee2a9c4015422655c
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="cxxframehandler"></a>__CxxFrameHandler
Fonction CRT interne. Utilisée par la bibliothèque CRT pour gérer les frames d'exceptions structurées.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
EXCEPTION_DISPOSITION __CxxFrameHandler(  
      EHExceptionRecord  *pExcept,  
      EHRegistrationNode *pRN,  
      void               *pContext,   
      DispatcherContext  *pDC  
   )  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pExcept`  
 Enregistrement d'exception qui est transmis aux instructions `catch` possibles.  
  
 `pRN`  
 Informations dynamiques sur le frame de pile utilisé pour gérer l'exception. Pour plus d'informations, voir ehdata.h.  
  
 `pContext`  
 Contexte. (Non utilisé sur les processeurs Intel.)  
  
 `pDC`  
 Informations supplémentaires sur l'entrée de la fonction et sur le frame de pile.  
  
## <a name="return-value"></a>Valeur de retour  
 Une des valeurs *d'expression de filtre* utilisées par [l’instruction try-except](../cpp/try-except-statement.md).  
  
## <a name="remarks"></a>Remarques  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|__CxxFrameHandler|excpt.h, ehdata.h|