---
title: _beginthread, _beginthreadex | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _beginthread
- _beginthreadex
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
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
dev_langs: C++
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
caps.latest.revision: "36"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 88da6a8a34670da588c0fef25b3060c79b3145f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="beginthread-beginthreadex"></a>_beginthread, _beginthreadex
Crée un thread.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
uintptr_t _beginthread( // NATIVE CODE  
   void( __cdecl *start_address )( void * ),  
   unsigned stack_size,  
   void *arglist   
);  
uintptr_t _beginthread( // MANAGED CODE  
   void( __clrcall *start_address )( void * ),  
   unsigned stack_size,  
   void *arglist   
);  
uintptr_t _beginthreadex( // NATIVE CODE  
   void *security,  
   unsigned stack_size,  
   unsigned ( __stdcall *start_address )( void * ),  
   void *arglist,  
   unsigned initflag,  
   unsigned *thrdaddr   
);  
uintptr_t _beginthreadex( // MANAGED CODE  
   void *security,  
   unsigned stack_size,  
   unsigned ( __clrcall *start_address )( void * ),  
   void *arglist,  
   unsigned initflag,  
   unsigned *thrdaddr   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `start_address`  
 Adresse de début d'une routine qui commence l'exécution d'un nouveau thread. Pour `_beginthread`, la convention d’appel est [__cdecl](../../cpp/cdecl.md) (pour le code natif) ou [__clrcall](../../cpp/clrcall.md) (pour le code managé). Pour `_beginthreadex`, il s’agit de [__stdcall](../../cpp/stdcall.md) (pour le code natif) ou [__clrcall](../../cpp/clrcall.md) (pour le code managé).  
  
 `stack_size`  
 Taille de la pile d'un nouveau thread ou 0.  
  
 `arglist`  
 Liste d'arguments à passer à un nouveau thread ou NULL.  
  
 `Security`  
 Pointeur vers une structure [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) qui détermine si le handle retourné peut être hérité par des processus enfants. Si `Security` est NULL, le handle ne peut pas être hérité. Doit avoir la valeur NULL pour les applications Windows 95.  
  
 `initflag`  
 Indicateurs qui contrôlent l'état initial d'un nouveau thread. Affectez `initflag` à la valeur `0` pour une exécution immédiate, ou `CREATE_SUSPENDED` pour créer le thread dans un état interrompu. Utilisez [ResumeThread](http://msdn.microsoft.com/library/windows/desktop/ms685086.aspx) pour exécuter le thread. Affectez à `initflag` l'indicateur `STACK_SIZE_PARAM_IS_A_RESERVATION` pour utiliser `stack_size` comme taille de réserve initiale de la pile en octets ; si cet indicateur n'est pas spécifié, `stack_size` spécifie la taille de validation.  
  
 `thrdaddr`  
 Pointe vers une variable 32 bits qui reçoit l'identificateur du thread. Si sa valeur est NULL, il n'est pas utilisé.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, chacune de ces fonctions retourne un handle au nouveau thread. Toutefois, si le nouveau thread se ferme trop rapidement, `_beginthread` peut ne pas retourner un handle valide. (Consultez la discussion dans la section Notes.) En cas d'erreur, `_beginthread` retourne -1L. Par ailleurs, `errno` prend la valeur `EAGAIN` s'il y a trop de threads, la valeur `EINVAL` si l'argument n'est pas valide ou si la taille de la pile est incorrecte, ou la valeur `EACCES` si les ressources sont insuffisantes (par exemple la mémoire). En cas d'erreur, `_beginthreadex` retourne 0 et `errno` et `_doserrno` sont définis.  
  
 Si `startaddress` a la valeur NULL, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent -1.  
  
 Pour plus d’informations sur ces codes de retour et d’autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour plus d’informations sur `uintptr_t`, consultez [Types standard](../../c-runtime-library/standard-types.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_beginthread` crée un thread qui commence l'exécution d'une routine à `start_address`. La routine à `start_address` doit utiliser la convention d'appel `__cdecl` (pour le code natif) ou `__clrcall` (pour le code managé) et ne doit pas avoir de valeur de retour. Lorsque le thread retourne de cette routine, il est terminé automatiquement. Pour plus d’informations sur les threads, consultez [Prise en charge du multithreading pour le code plus ancien (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 `_beginthreadex` ressemble plus à l’API [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453.aspx) Win32 que `_beginthread`. `_beginthreadex` diffère de `_beginthread` des façons suivantes :  
  
-   `_beginthreadex` a trois paramètres supplémentaires : `initflag`, `security` et `threadaddr`. Le nouveau thread peut être créé dans un état suspendu, avec une sécurité spécifiée, et il est accessible à l'aide de `thrdaddr`, qui représente l'identificateur du thread.  
  
-   La routine à `start_address` passée à `_beginthreadex` doit utiliser la convention d'appel `__stdcall` (pour le code natif) ou `__clrcall` (pour le code managé) et doit retourner un code de sortie de thread.  
  
-   `_beginthreadex` retourne 0 en cas d'échec plutôt que -1L.  
  
-   Un thread créé à l’aide de `_beginthreadex` est arrêté par un appel à [_endthreadex](../../c-runtime-library/reference/endthread-endthreadex.md).  
  
 La fonction `_beginthreadex` vous permet de mieux contrôler la création du thread que `_beginthread` . La fonction `_endthreadex` est également plus flexible. Par exemple, avec `_beginthreadex`, vous pouvez utiliser les informations de sécurité, définir l'état initial du thread (en cours d'exécution ou suspendu) et obtenir l'identificateur du thread nouvellement créé. Vous pouvez également utiliser le handle du thread qui est retourné par `_beginthreadex` avec les API de synchronisation, ce que vous ne pouvez pas faire avec `_beginthread`.  
  
 Il est préférable d'utiliser `_beginthreadex` au lieu de `_beginthread`. Si le thread généré par `_beginthread` se ferme rapidement, le handle retourné à l'appelant de `_beginthread` peut être non valide ou pointer sur un autre thread. Toutefois, le handle retourné par `_beginthreadex` doit être fermé par l'appelant de `_beginthreadex`. Il s'agit donc forcément d'un handle valide si `_beginthreadex` n'a pas retourné d'erreur.  
  
 Vous pouvez appeler [_endthread](../../c-runtime-library/reference/endthread-endthreadex.md) ou `_endthreadex` explicitement pour terminer un thread ; toutefois, `_endthread` ou `_endthreadex` est appelé automatiquement quand le thread retourne de la routine passée comme paramètre. La fin d'un thread par un appel à `_endthread` ou `_endthreadex` permet de garantir une récupération correcte des ressources allouées pour le thread.  
  
 `_endthread` ferme automatiquement le handle de thread, ce qui n'est pas le cas de `_endthreadex`. Ainsi, quand vous utilisez `_beginthread` et `_endthread`, ne fermez pas explicitement le handle du thread en appelant l’API [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) Win32. Ce comportement diffère de l’API [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) Win32.  
  
> [!NOTE]
>  Pour un fichier exécutable lié à Libcmt.lib, n'appelez pas l'API Win32 `ExitThread` afin de ne pas empêcher le système runtime de récupérer les ressources allouées. `_endthread` et `_endthreadex` récupèrent les ressources de thread allouées, puis appellent `ExitThread`.  
  
 Le système d'exploitation gère l'allocation de la pile lorsque `_beginthread` ou `_beginthreadex` est appelé ; vous n'êtes pas obligé de passer l'adresse de la pile des threads à l'une ou l'autre de ces fonctions. En outre, l'argument `stack_size` peut être 0, auquel cas le système d'exploitation utilise la même valeur que la pile spécifiée pour le thread principal.  
  
 `arglist` est un paramètre à passer au thread nouvellement créé. En général, il s'agit de l'adresse d'un élément de donnée, tel qu'une chaîne de caractères. `arglist` peut être null s'il n'est pas nécessaire, mais `_beginthread` et `_beginthreadex` doivent avoir une valeur à passer au nouveau thread. Tous les threads sont arrêtés si un thread appelle `abort`, `exit`, `_exit`, ou `ExitProcess`.  
  
 Les paramètres régionaux du nouveau thread sont hérités de son thread parent. Si les paramètres régionaux par thread sont activés par un appel à [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md) (globalement ou pour de nouveaux threads uniquement), le thread peut modifier ses paramètres régionaux indépendamment de son parent en appelant `setlocale` ou `_wsetlocale`. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Pour le code mixte et pure, `_beginthread` et `_beginthreadex` ont chacun deux surcharges. L'une accepte un pointeur de fonction à convention d'appel native, l'autre accepte un pointeur de fonction `__clrcall` . La première surcharge n'est pas sécurisée au niveau du domaine d'application et ne le sera jamais. Si vous écrivez du code mixte ou du code pure, vous devez vérifier que le nouveau thread accède au domaine d'application correct avant d'accéder à des ressources managées. Pour cela, vous pouvez par exemple utiliser la [fonction call_in_appdomain](../../dotnet/call-in-appdomain-function.md). La seconde surcharge est sécurisée au niveau du domaine d'application ; le nouveau thread finit toujours dans le domaine d'application de l'appelant de `_beginthread` ou `_beginthreadex`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_beginthread`|\<process.h>|  
|`_beginthreadex`|\<process.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions multithread des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
 Pour utiliser `_beginthread` ou `_beginthreadex`, l'application doit être liée à l'une des bibliothèques multithread Runtime C.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant utilise `_beginthread` et `_endthread`.  
  
```  
// crt_BEGTHRD.C  
// compile with: /MT /D "_X86_" /c  
// processor: x86  
#include <windows.h>  
#include <process.h>    /* _beginthread, _endthread */  
#include <stddef.h>  
#include <stdlib.h>  
#include <conio.h>  
  
void Bounce( void * );  
void CheckKey( void * );  
  
// GetRandom returns a random integer between min and max.  
#define GetRandom( min, max ) ((rand() % (int)(((max) + 1) - (min))) + (min))  
// GetGlyph returns a printable ASCII character value  
#define GetGlyph( val ) ((char)((val + 32) % 93 + 33))  
  
BOOL repeat = TRUE;                 // Global repeat flag   
HANDLE hStdOut;                     // Handle for console window  
CONSOLE_SCREEN_BUFFER_INFO csbi;    // Console information structure  
  
int main()  
{  
    int param = 0;  
    int * pparam = &param;  
  
    // Get display screen's text row and column information.  
    hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );  
    GetConsoleScreenBufferInfo( hStdOut, &csbi );  
  
    // Launch CheckKey thread to check for terminating keystroke.  
    _beginthread( CheckKey, 0, NULL );  
  
    // Loop until CheckKey terminates program or 1000 threads created.   
    while( repeat && param < 1000 )  
    {  
        // launch another character thread.  
        _beginthread( Bounce, 0, (void *) pparam );  
  
        // increment the thread parameter  
        param++;  
  
        // Wait one second between loops.  
        Sleep( 1000L );  
    }  
}  
  
// CheckKey - Thread to wait for a keystroke, then clear repeat flag.  
void CheckKey( void * ignored )  
{  
    _getch();  
    repeat = 0;    // _endthread implied  
}  
  
// Bounce - Thread to create and and control a colored letter that moves  
// around on the screen.  
//  
// Params: parg - the value to create the character from  
void Bounce( void * parg )  
{  
    char       blankcell = 0x20;  
    CHAR_INFO  ci;  
    COORD      oldcoord, cellsize, origin;  
    DWORD      result;  
    SMALL_RECT region;  
  
    cellsize.X = cellsize.Y = 1;  
    origin.X = origin.Y = 0;  
  
    // Generate location, letter and color attribute from thread argument.  
    srand( _threadid );  
    oldcoord.X = region.Left = region.Right =   
        GetRandom(csbi.srWindow.Left, csbi.srWindow.Right - 1);  
    oldcoord.Y = region.Top = region.Bottom =   
        GetRandom(csbi.srWindow.Top, csbi.srWindow.Bottom - 1);  
    ci.Char.AsciiChar = GetGlyph(*((int *)parg));  
    ci.Attributes = GetRandom(1, 15);  
  
    while (repeat)  
    {  
        // Pause between loops.  
        Sleep( 100L );  
  
        // Blank out our old position on the screen, and draw new letter.  
        WriteConsoleOutputCharacterA(hStdOut, &blankcell, 1, oldcoord, &result);  
        WriteConsoleOutputA(hStdOut, &ci, cellsize, origin, &region);  
  
        // Increment the coordinate for next placement of the block.  
        oldcoord.X = region.Left;  
        oldcoord.Y = region.Top;  
        region.Left = region.Right += GetRandom(-1, 1);  
        region.Top = region.Bottom += GetRandom(-1, 1);  
  
        // Correct placement (and beep) if about to go off the screen.  
        if (region.Left < csbi.srWindow.Left)  
            region.Left = region.Right = csbi.srWindow.Left + 1;  
        else if (region.Right >= csbi.srWindow.Right)  
            region.Left = region.Right = csbi.srWindow.Right - 2;  
        else if (region.Top < csbi.srWindow.Top)  
            region.Top = region.Bottom = csbi.srWindow.Top + 1;  
        else if (region.Bottom >= csbi.srWindow.Bottom)  
            region.Top = region.Bottom = csbi.srWindow.Bottom - 2;  
  
        // If not at a screen border, continue, otherwise beep.  
        else  
            continue;  
        Beep((ci.Char.AsciiChar - 'A') * 100, 175);  
    }  
    // _endthread given to terminate  
    _endthread();  
}  
```  
  
 Appuyez sur n'importe quelle touche pour fermer l'exemple d'application.  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant montre comment utiliser le handle de thread retourné par `_beginthreadex` avec l’API de synchronisation [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx). Le thread principal attend que le second thread se termine avant de continuer. Lorsque le deuxième thread appelle `_endthreadex`, il fait passer son objet thread à l'état signalé. Le thread principal peut ainsi continuer à s'exécuter. Cela ne peut pas être fait avec `_beginthread` et `_endthread`, car `_endthread` appelle `CloseHandle`, qui détruit l'objet thread avant de pouvoir le définir avec l'état signalé.  
  
```  
// crt_begthrdex.cpp  
// compile with: /MT  
#include <windows.h>  
#include <stdio.h>  
#include <process.h>  
  
unsigned Counter;   
unsigned __stdcall SecondThreadFunc( void* pArguments )  
{  
    printf( "In second thread...\n" );  
  
    while ( Counter < 1000000 )  
        Counter++;  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
int main()  
{   
    HANDLE hThread;  
    unsigned threadID;  
  
    printf( "Creating second thread...\n" );  
  
    // Create the second thread.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc, NULL, 0, &threadID );  
  
    // Wait until second thread terminates. If you comment out the line  
    // below, Counter will not be correct because the thread has not  
    // terminated, and Counter most likely has not been incremented to  
    // 1000000 yet.  
    WaitForSingleObject( hThread, INFINITE );  
    printf( "Counter should be 1000000; it is-> %d\n", Counter );  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
```Output  
Creating second thread...  
In second thread...  
Counter should be 1000000; it is-> 1000000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [_endthread, _endthreadex](../../c-runtime-library/reference/endthread-endthreadex.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)