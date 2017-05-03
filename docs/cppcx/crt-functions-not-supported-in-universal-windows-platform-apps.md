---
title: "Fonctions CRT non prises en charge dans les applications de la plateforme Windows universelle | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbfc957d-6c60-48f4-97e3-1ed8526743b4
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# Fonctions CRT non prises en charge dans les applications de la plateforme Windows universelle
Plusieurs fonctions CRT \(C runtime\) ne sont pas disponibles quand vous créez des applications pour la plateforme Windows universelle \(UWP\). Dans certains cas, des solutions de contournement sont disponibles : par exemple, vous pouvez utiliser [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ou les API Win32. Toutefois, dans d’autres cas, les fonctions CRT sont exclues, car les fonctionnalités qui leur correspondent ou les API de prise en charge ne sont pas applicables aux applications UWP.  
  
 Le tableau suivant répertorie les fonctions CRT qui ne sont pas disponibles quand vous créez des applications UWP, et indique les éventuelles solutions de contournement applicables.  
  
## Fonctions CRT non prises en charge  
  
||||  
|-|-|-|  
|\_beep \_sleep \_seterrormode|Ces fonctions sont obsolètes dans les versions précédentes de CRT. En outre, les API Win32 correspondantes ne sont pas disponibles pour les applications UWP.|Aucune solution de contournement.|  
|chdir \_chdrive getcwd|Ces fonctions sont obsolètes ou ne sont pas thread\-safe.|Utilisez \_chdir, \_getcwd et les fonctions connexes.|  
|\_cgets \_cgets\_s \_cgetws \_cgetws\_s \_cprintf \_cprintf\_l \_cprintf\_p \_cprintf\_p\_l \_cprintf\_s \_cprintf\_s\_l \_cputs \_cputws \_cscanf \_cscanf\_l \_cscanf\_s \_cscanf\_s\_l \_cwait \_cwprintf \_cwprintf\_l \_cwprintf\_p \_cwprintf\_p\_l \_cwprintf\_s \_cwprintf\_s\_l \_cwscanf \_cwscanf\_l \_cwscanf\_s \_cwscanf\_s\_l \_vcprintf \_vcprintf\_l \_vcprintf\_p \_vcprintf\_p\_l \_vcprintf\_s \_vcprintf\_s\_l \_vcwprintf \_vcwprintf\_l \_vcwprintf\_p \_vcwprintf\_p\_l \_vcwprintf\_s \_vcwprintf\_s\_l \_getch \_getch\_nolock \_getche \_getche\_nolock \_getwch \_getwch\_nolock \_getwche \_getwche\_nolock \_putch \_putch\_nolock \_putwch \_putwch\_nolock \_ungetch \_ungetch\_nolock \_ungetwch \_ungetwch\_nolock \_kbhit kbhit putch cgets cprintf cputs cscanf cwait getch getche ungetch|Ces fonctions sont utilisées pour lire et écrire directement dans la console. Les applications UWP ne fonctionnent qu’avec les GUI. Elles ne prennent pas de console en charge.|Aucune solution de contournement.|  
|getpid|Cette fonction est obsolète.|Utilisez \_getpid ou l’API Win32 `GetCurrentProcessId()`.|  
|\_getdiskfree|Non disponible.|Utilisez l’API Win32 `GetDiskFreeSpaceExW()`.|  
|\_getdrive \_getdrives|L’API correspondante n’est pas disponible pour les applications UWP.|Aucune solution de contournement.|  
|\_inp \_inpd \_inpw \_outp \_outpd \_outpw inp inpd inpw outp outpd outpw|E\/S de port non pris en charge dans les applications UWP.|Aucune solution de contournement.|  
|\_ismbcalnum \_ismbcalnum\_l \_ismbcalpha \_ismbcalpha\_l \_ismbcdigit \_ismbcdigit\_l \_ismbcgraph \_ismbcgraph\_l \_ismbchira \_ismbchira\_l \_ismbckata \_ismbckata\_l \_ismbcl0 \_ismbcl0\_l \_ismbcl1 \_ismbcl1\_l \_ismbcl2 \_ismbcl2\_l \_ismbclegal \_ismbclegal\_l \_ismbclower \_ismbclower\_l \_ismbcprint \_ismbcprint\_l \_ismbcpunct \_ismbcpunct\_l \_ismbcspace \_ismbcspace\_l \_ismbcsymbol \_ismbcsymbol\_l \_ismbcupper \_ismbcupper\_l \_mbbtombc \_mbbtombc\_l \_mbbtype \_mbbtype\_l \_mbccpy \_mbccpy\_l \_mbccpy\_s \_mbccpy\_s\_l \_mbcjistojms \_mbcjistojms\_l \_mbcjmstojis \_mbcjmstojis\_l \_mbclen \_mbclen\_l \_mbctohira \_mbctohira\_l \_mbctokata \_mbctokata\_l \_mbctolower \_mbctolower\_l \_mbctombb \_mbctombb\_l \_mbctoupper \_mbctoupper\_l \_mbsbtype \_mbsbtype\_l \_mbscat \_mbscat\_l \_mbscat\_s \_mbscat\_s\_l \_mbschr \_mbschr\_l \_mbscmp \_mbscmp\_l \_mbscoll \_mbscoll\_l \_mbscpy \_mbscpy\_l \_mbscpy\_s \_mbscpy\_s\_l \_mbscspn \_mbscspn\_l \_mbsdec \_mbsdec\_l \_mbsicmp \_mbsicmp\_l \_mbsicoll \_mbsicoll\_l \_mbsinc \_mbsinc\_l \_mbslen \_mbslen\_l \_mbslwr \_mbslwr\_l \_mbslwr\_s \_mbslwr\_s\_l \_mbsnbcat \_mbsnbcat\_l \_mbsnbcat\_s \_mbsnbcat\_s\_l \_mbsnbcmp \_mbsnbcmp\_l \_mbsnbcnt \_mbsnbcnt\_l \_mbsnbcoll \_mbsnbcoll\_l \_mbsnbcpy \_mbsnbcpy\_l \_mbsnbcpy\_s \_mbsnbcpy\_s\_l \_mbsnbicmp \_mbsnbicmp\_l \_mbsnbicoll \_mbsnbicoll\_l \_mbsnbset \_mbsnbset\_l \_mbsnbset\_s \_mbsnbset\_s\_l \_mbsncat \_mbsncat\_l \_mbsncat\_s \_mbsncat\_s\_l \_mbsnccnt \_mbsnccnt\_l \_mbsncmp \_mbsncmp\_l \_mbsncoll \_mbsncoll\_l \_mbsncpy \_mbsncpy\_l \_mbsncpy\_s \_mbsncpy\_s\_l \_mbsnextc \_mbsnextc\_l \_mbsnicmp \_mbsnicmp\_l \_mbsnicoll \_mbsnicoll\_l \_mbsninc \_mbsninc\_l \_mbsnlen \_mbsnlen\_l \_mbsnset \_mbsnset\_l \_mbsnset\_s \_mbsnset\_s\_l \_mbspbrk \_mbspbrk\_l \_mbsrchr \_mbsrchr\_l \_mbsrev \_mbsrev\_l \_mbsset \_mbsset\_l \_mbsset\_s \_mbsset\_s\_l \_mbsspn \_mbsspn\_l \_mbsspnp \_mbsspnp\_l \_mbsstr \_mbsstr\_l \_mbstok \_mbstok\_l \_mbstok\_s \_mbstok\_s\_l \_mbsupr \_mbsupr\_l \_mbsupr\_s \_mbsupr\_s\_l is\_wctype|Les chaînes multioctets ne sont pas prises en charge dans les applications UWP.|Utilisez des chaînes Unicode à la place.|  
|\_pclose \_pipe \_popen \_wpopen|La fonctionnalité pipe n’est pas disponible pour les applications UWP.|Aucune solution de contournement.|  
|\_resetstkoflw|Les API Win32 de prise en charge ne sont pas disponibles pour les applications UWP.|Aucune solution de contournement.|  
|\_getsystime \_setsystime|Il s’agit d’API obsolètes dans les versions précédentes de CRT. En outre, un utilisateur ne peut pas définir l’heure système dans une application UWP en raison d’un manque d’autorisations.|Pour obtenir uniquement l’heure système, utilisez l’API Win32 `GetSystemTime`. Impossible de définir l’heure système.|  
|\_environ \_putenv \_putenv\_s \_searchenv \_searchenv\_s \_dupenv\_s \_wputenv \_wputenv\_s \_wsearchenv getenv getenv\_s putenv \_wdupenv\_s \_wenviron \_wgetenv \_wgetenv\_s \_wsearchenv\_s tzset|Les variables d’environnement ne sont pas disponibles pour les applications UWP.|Aucune solution de contournement. Pour définir le fuseau horaire, utilisez \_tzset.|  
|\_loaddll \_getdllprocaddr \_unloaddll|Il s’agit de fonctions obsolètes dans les versions précédentes de CRT. En outre, l’utilisateur ne peut pas charger les DLL, à l’exception de celles figurant dans le même package d’application.|Utilisez les API Win32 `LoadPackagedLibrary`, `GetProcAddress` et `FreeLibrary` pour charger et utiliser les DLL packagées.|  
|\_wexecl \_wexecle \_wexeclp \_wexeclpe \_wexecv \_wexecve \_wexecvp \_wexecvpe \_execl \_execle \_execlp \_execlpe \_execv \_execve \_execvp \_execvpe \_spawnl \_spawnle \_spawnlp \_spawnlpe \_spawnv \_spawnve \_spawnvp \_spawnvpe \_wspawnl \_wspawnle \_wspawnlp \_wspawnlpe \_wspawnv \_wspawnve \_wspawnvp \_wspawnvpe \_wsystem execl execle execlp execlpe execv execve execvp execvpe spawnl spawnle spawnlp spawnlpe spawnv spawnve spawnvp spawnvpe system|La fonctionnalité n’est pas disponible dans les applications UWP. Une application UWP ne peut pas appeler une autre application UWP ou une application de bureau.|Aucune solution de contournement.|  
|\_heapwalk \_heapadd \_heapchk \_heapset \_heapused|Ces fonctions sont généralement utilisées avec le tas. Toutefois, les API Win32 correspondantes ne sont pas prises en charge dans les applications UWP. De plus, les applications ne peuvent plus créer ou utiliser les tas privés.|Aucune solution de contournement. Toutefois, `_heapwalk` est disponible dans DEBUG CRT, à des fins de débogage uniquement. Ces fonctions ne peuvent pas être utilisées dans les applications téléchargées dans le Windows Store.|  
  
 Les fonctions suivantes sont disponibles dans CRT pour les applications UWP, mais doivent être utilisées uniquement quand les API Win32 ou [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] correspondantes ne peuvent pas être utilisées, par exemple, quand vous déplacez des bases de code volumineuses  
  
|||  
|-|-|  
|Fonctions de chaîne simple octet : par exemple, `strcat`, `strcpy`, `strlwr`, et ainsi de suite.|Vos applications UWP doivent être strictement Unicode, car toutes les API Win32 et les API [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] exposées utilisent des jeux de caractères Unicode uniquement. Les fonctions simple octet sont réservées au portage de bases de code volumineuses ou doivent être évitées. Les fonctions wide char correspondantes doivent être utilisées à la place quand cela est possible.|  
|Fonctions d’E\/S de flux ou d’E\/S de fichier de bas niveau, par exemple, `fopen`, `open` et ainsi de suite.|Ces fonctions sont synchrones, ce qui n’est pas recommandé pour les applications UWP. Dans vos applications UWP, utilisez des API asynchrones pour ouvrir, lire et écrire dans des fichiers afin d’éviter le verrouillage du thread d’interface utilisateur. Ces API sont, par exemple, celles de la classe `Windows::Storage::FileIO`.|  
  
## Applications du Windows 8.x Store et applications Windows Phone 8.x  
 Outre les API mentionnées précédemment, les API suivantes ne sont pas disponibles dans les applications du Windows 8.x Store et les applications Windows Phone 8.x.  
  
||||  
|-|-|-|  
|\_beginthread \_beginthreadex \_endthread \_endthreadex|Les API Win32 de thread ne sont pas disponibles dans les applications du Windows 8.x Store.|Utilisez `Windows Runtime Windows::System::Threading::ThreadPool` ou `concurrency::task` à la place.|  
|\_chdir \_wchdir \_getcwd \_getdcwd \_wgetcwd \_wgetdcwd|Le concept d’un répertoire de travail ne s’applique pas aux applications du Windows 8.x Store.|Utilisez plutôt des chemins complets.|  
|\_getpid|Cette fonction est obsolète dans les versions précédentes de CRT.|Utilisez l’API Win32 `GetCurrentProcessId()`|  
|\_isleadbyte\_l \_ismbbalnum, \_ismbbalnum\_l, \_ismbbalpha, \_ismbbalpha \_ismbbalpha\_l \_ismbbgraph \_ismbbgraph\_l \_ismbbkalnum \_ismbbkalnum\_l \_ismbbkana \_ismbbkana\_l \_ismbbkprint \_ismbbkprint\_l \_ismbbkpunct \_ismbbkpunct\_l \_ismbblead \_ismbblead\_l \_ismbbprint \_ismbbprint\_l \_ismbbpunct \_ismbbpunct\_l \_ismbbtrail \_ismbbtrail\_l \_ismbslead \_ismbslead\_l \_ismbstrail \_ismbstrail\_l \_mbsdup isleadbyte|Les chaînes multioctets ne sont pas prises en charge dans les applications du Windows 8.x Store.|Utilisez des chaînes Unicode à la place.|  
|\_tzset|Les variables d’environnement ne sont pas disponibles pour les applications du Windows 8.x Store.|Aucune solution de contournement.|  
|\_get\_heap\_handle, \_heapmin|Les API Win32 correspondantes ne sont pas prises en charge dans les applications du Windows 8.x Store. De plus, les applications ne peuvent plus créer de tas privé.|Aucune solution de contournement. Toutefois, `_get_heap_handle` est disponible dans DEBUG CRT, à des fins de débogage uniquement.|