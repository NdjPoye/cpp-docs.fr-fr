---
title: __security_init_cookie | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __security_init_cookie
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
apitype: DLLExport
f1_keywords:
- security_init_cookie
- __security_init_cookie
dev_langs: C++
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee0657393ec8322889b527c21a36c13b9e032325
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="securityinitcookie"></a>__security_init_cookie
Initialise le cookie de sécurité global.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __security_init_cookie(void);  
```  
  
## <a name="remarks"></a>Notes  
 Le cookie de sécurité global est utilisé pour la protection contre le dépassement de mémoire tampon dans le code compilé avec [GS (Vérification de la sécurité de la mémoire tampon)](../../build/reference/gs-buffer-security-check.md), ainsi que dans le code qui utilise la gestion des exceptions. À l'entrée dans une fonction protégée contre le dépassement de mémoire tampon, le cookie est placé dans la pile. À la sortie, sa valeur dans la pile est comparée à celle du cookie global. Toute différence de valeur indique qu'un dépassement de mémoire tampon s'est produit, ce qui entraîne l'arrêt immédiat du programme.  
  
 En règle générale, `__security_init_cookie` est appelé par le CRT quand il est initialisé. Si vous ignorez l’initialisation CRT (par exemple, si vous utilisez [/ENTRY](../../build/reference/entry-entry-point-symbol.md) pour spécifier un point d’entrée), vous devez vous-même appeler `__security_init_cookie`. Si `__security_init_cookie` n'est pas appelé, une valeur par défaut est affectée au cookie de sécurité global. Par ailleurs, la protection contre le dépassement de mémoire tampon est compromise. Dans la mesure où un pirate peut exploiter cette valeur de cookie par défaut pour tromper les contrôles de dépassement de mémoire tampon, nous vous recommandons de toujours appeler `__security_init_cookie` quand vous définissez votre propre point d'entrée.  
  
 L'appel de `__security_init_cookie` doit intervenir avant l'entrée dans une fonction protégée contre le dépassement de mémoire tampon. Sinon, un dépassement de mémoire tampon parasite est détecté. Pour plus d’informations, consultez [Erreur R6035 du Runtime C](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## <a name="example"></a>Exemple  
 Consultez les exemples présentés dans [Erreur R6035 du Runtime C](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`__security_init_cookie`|\<process.h>|  
  
 `__security_init_cookie` est une extension Microsoft de la bibliothèque Runtime C standard. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles approfondis de la sécurité du compilateur](http://go.microsoft.com/fwlink/p/?linkid=7260)