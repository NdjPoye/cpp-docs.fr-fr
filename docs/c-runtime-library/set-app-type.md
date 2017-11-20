---
title: _set_app_type | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_app_type
apilocation: api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
dev_langs: C++
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 86078a8ff66eadc1cdd6b177ba074abfd1683345
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="setapptype"></a>_set_app_type
Fonction interne utilisée au démarrage pour indiquer à la bibliothèque CRT si l’application est une application console ou une application GUI.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef enum _crt_app_type
{
    _crt_unknown_app,
    _crt_console_app,
    _crt_gui_app
} _crt_app_type;

void __cdecl _set_app_type(
    _crt_app_type appType
    ); 
```  
  
## <a name="parameters"></a>Paramètres  
 `appType`  
 Valeur qui indique le type d’application. Les valeurs possibles sont :  
  
|Valeur|Description|  
|----------------|-----------------|  
|_crt_unknown_app|Type d’application inconnu.|  
|_crt_console_app|Application console (ligne de commande).|  
|_crt_gui_app|Application GUI (Windows).|  
  
## <a name="remarks"></a>Remarques  
 Normalement, il est inutile d’appeler cette fonction. Elle fait partie du code de démarrage du runtime C qui s’exécute avant que `main` ne soit appelé dans votre application.
 
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|_set_app_type|process.h|

