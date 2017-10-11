---
title: _initterm, _initterm_e | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _initterm_e
- _initterm
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _initterm_e
- initterm
- _initterm
- initterm_e
dev_langs:
- C++
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 377f8e19268a643b0237da66ba14a82fc7b6685b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="initterm-initterme"></a>_initterm, _initterm_e
Méthodes internes qui parcourent un tableau de pointeurs de fonction et les initialisent.  
  
 Le premier pointeur est l’emplacement de départ dans le tableau et le deuxième pointeur est l’emplacement de fin.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __cdecl _initterm(  
   PVFV *,  
   PVFV *  
);  
  
int __cdecl _initterm_e(  
   PVFV *,  
   PVFV *  
);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Code d’erreur différent de zéro si l’initialisation échoue et génère une erreur ; 0 si aucune erreur ne se produit.  
  
## <a name="remarks"></a>Notes  
 Ces méthodes sont appelées uniquement en interne pendant l’initialisation d’un programme C++. N’appelez pas ces méthodes dans un programme.  
  
 Quand ces méthodes parcourent un tableau d’entrées de fonction, elles ignorent les entrées `NULL`.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)
