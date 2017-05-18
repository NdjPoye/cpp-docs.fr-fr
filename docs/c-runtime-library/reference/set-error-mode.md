---
title: _set_error_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_error_mode
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
- set_error_mode
- _set_error_mode
dev_langs:
- C++
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 205a6bed342ce1489664a5e9e37880612492b04d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="seterrormode"></a>_set_error_mode
Modifie `__error_mode` pour déterminer un emplacement autre que celui utilisé par défaut dans lequel le Runtime C écrit un message d'erreur pour une erreur qui risque de mettre fin au programme.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _set_error_mode(  
   int modeval   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `modeval`  
 Destination des messages d'erreur.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne l'ancien paramètre ou -1 si une erreur se produit.  
  
## <a name="remarks"></a>Notes  
 Contrôle l'intercepteur de sortie d'erreurs en définissant la valeur de `__error_mode`. Par exemple, vous pouvez diriger la sortie vers une erreur standard ou utiliser l'API `MessageBox`.  
  
 Le paramètre `modeval` peut avoir l'une des valeurs suivantes.  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_OUT_TO_DEFAULT`|L'intercepteur d'erreurs est déterminé par `__app_type`.|  
|`_OUT_TO_STDERR`|L'intercepteur d'erreurs est une erreur standard.|  
|`_OUT_TO_MSGBOX`|L'intercepteur d'erreurs est une boîte de message.|  
|`_REPORT_ERRMODE`|Fait état de la valeur actuelle de `__error_mode`.|  
  
 Si la valeur transmise est différente de celles répertoriées, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `_set_error_mode` affecte à `errno` la valeur `EINVAL` et retourne -1.  
  
 Quand elle est utilisée avec [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md), la routine `_set_error_mode` affiche l’instruction en échec dans la boîte de dialogue et vous donne la possibilité de choisir le bouton `Ignore` pour permettre la poursuite de l’exécution du programme.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_set_error_mode`|\<stdlib.h>|  
  
## <a name="example"></a>Exemple  
  
```C  
// crt_set_error_mode.c  
// compile with: /c  
#include <stdlib.h>  
#include <assert.h>  
  
int main()  
{  
   _set_error_mode(_OUT_TO_STDERR);  
   assert(2+2==5);  
}  
```  
  
```Output  
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8  
  
This application has requested the Runtime to terminate it in an unusual way.  
Please contact the application's support team for more information.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [assert Macro, _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)
