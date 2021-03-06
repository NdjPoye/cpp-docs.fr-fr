---
title: terminate (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- terminate
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
- terminate
dev_langs:
- C++
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c743439b487f091b760e3747c47b471832e1ff3d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="terminate-crt"></a>terminate (CRT)

Appels [abandonner](abort.md) ou une fonction que vous spécifiez à l’aide de **set_terminate**.

## <a name="syntax"></a>Syntaxe

```C
void terminate( void );
```

## <a name="remarks"></a>Notes

Le **Terminer** fonction est utilisée avec la gestion des exceptions C++ et est appelée dans les cas suivants :

- Gestionnaire catch correspondant introuvable pour une exception C++ levée.

- Exception levée par une fonction destructeur pendant un désempilage.

- Pile endommagée après la levée d’une exception.

**Terminer** appelle [abandonner](abort.md) par défaut. Vous pouvez modifier cette valeur par défaut en écrivant votre propre fonction d’arrêt et en appelant **set_terminate** avec le nom de votre fonction comme argument. **Terminer** appelle la dernière fonction donnée comme argument à **set_terminate**. Pour plus d’informations, consultez [Exceptions C++ non gérées](../../cpp/unhandled-cpp-exceptions.md).

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**terminate**|\<eh.h>|

Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

```cpp
// crt_terminate.cpp
// compile with: /EHsc
#include <eh.h>
#include <process.h>
#include <iostream>
using namespace std;

void term_func();

int main()
{
    int i = 10, j = 0, result;
    set_terminate( term_func );
    try
    {
        if( j == 0 )
            throw "Divide by zero!";
        else
            result = i/j;
    }
    catch( int )
    {
        cout << "Caught some integer exception.\n";
    }
    cout << "This should never print.\n";
}

void term_func()
{
    cout << "term_func() was called by terminate().\n";

    // ... cleanup tasks performed here

    // If this function does not exit, abort is called.

    exit(-1);
}
```

```Output
term_func() was called by terminate().
```

## <a name="see-also"></a>Voir aussi

[Routines de gestion des exceptions](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
