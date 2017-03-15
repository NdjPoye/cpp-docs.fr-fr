---
title: "Comportement de la biblioth&#232;que runtime | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_DllMainCRTStartup"
  - "CRT_INIT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CRT_INIT (macro)"
  - "_DllMainCRTStartup (méthode)"
  - "DllMain (fonction)"
  - "DLL (C++), fonction de point d'entrée"
  - "DLL (C++), comportement de la bibliothèque Runtime"
  - "DLL (C++), séquence de démarrage"
  - "attacher un processus (C++)"
  - "détacher un processus (C++)"
  - "au moment de l'exécution (C++), séquence de démarrage DLL"
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Comportement de la biblioth&#232;que runtime
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le code de la bibliothèque Runtime C\/C\+\+ exécute la séquence de démarrage de la DLL, rendant ainsi superflue la liaison avec un module séparé qui était nécessaire sous Windows 3.x.  Le code de la bibliothèque Runtime C\/C\+\+ inclut la fonction de point d'entrée de la DLL appelée **\_DllMainCRTStartup**.  La fonction **\_DllMainCRTStartup** accomplit plusieurs tâches, notamment l'appel de **\_CRT\_INIT**, qui initialise la bibliothèque Runtime C\/C\+\+ et sollicite les constructeurs C\+\+ sur les variables non\-locales statiques.  Sans cette fonction, la bibliothèque runtime resterait non initialisée.  **\_CRT\_INIT** est disponible à la fois pour un CRT lié de manière statique et pour la liaison à la CRT DLL Msvcr90.dll à partir d'une DLL utilisateur.  
  
 S'il est possible de spécifier une autre fonction de point d'entrée à l'aide de l'option de l'éditeur de liens \/ENTRY:, cette opération n'est pas recommandée car la fonction de point d'entrée aurait à dupliquer tout ce que fait **\_DllMainCRTStartup**.  Lorsque vous générez des DLL dans Visual C\+\+, **\_DllMainCRTStartup** est liée automatiquement et vous n'avez pas besoin de spécifier une fonction de point d'entrée à l'aide de l'option\/ENTRY: de l'éditeur de liens.  
  
 Outre l'initialisation de la bibliothèque Runtime C, **\_DllMainCRTStartup** appelle une fonction dénommée `DllMain`.  Selon le type de DLL que vous générez, Visual C\+\+ fournit `DllMain` et établit une liaison afin que **\_DllMainCRTStartup** puisse toujours avoir quelque chose à appeler.  De cette façon, si vous n'avez pas besoin d'initialiser la DLL, il ne vous reste rien de spécial à faire lors de la génération de la DLL.  Si vous devez initialiser la DLL, l'emplacement où vous ajoutez le code dépend du type de DLL que vous écrivez.  Pour plus d'informations, consultez [Initialisation d'une DLL](../build/initializing-a-dll.md).  
  
 La bibliothèque runtime du C\/C\+\+ appelle des constructeurs et des destructeurs sur les variables non\-locales statiques.  Par exemple, dans le code source de DLL suivant, `Equus` et `Sugar` sont deux objets statiques, non locaux de la classe `CHorse`, défini dans Horses.h.  Il n'y a aucune fonction dans le code source qui contient des appels à une fonction constructeur pour `CHorse` ou à la fonction destructeur parce que ces objets sont définis en dehors de toute fonction.  Par conséquent, les appels à ces constructeurs et destructeurs doivent être réalisés par le code d'exécution.  Le code de la bibliothèque runtime pour les applications remplit également cette fonction.  
  
```  
#include "horses.h"  
  
CHorse  Equus( ARABIAN, MALE );  
CHorse  Sugar( THOROUGHBRED, FEMALE );  
  
BOOL    WINAPI   DllMain (HANDLE hInst,   
                            ULONG ul_reason_for_call,  
                            LPVOID lpReserved)  
...  
```  
  
 Chaque fois qu'un nouveau processus essaie d'utiliser la DLL, le système d'exploitation crée une copie séparée des données de la DLL : cette opération est appelée « attachement de processus ».  Le code de la bibliothèque runtime de la DLL appelle les constructeurs pour tous les objets globaux le cas échéant, puis appelle la fonction `DllMain` avec l'attachement de processus sélectionné.  L'opération inverse est le détachement de processus : le code de la bibliothèque runtime appelle `DllMain` avec le détachement de processus sélectionné puis appelle une liste de fonctions d'arrêt, y compris les fonctions `atexit`, les destructeurs des objets globaux et les destructeurs des objets statiques.  Notez que l'ordre des événements dans l'attachement de processus est l'inverse de celui du détachement de processus.  
  
 Le code de la bibliothèque runtime est également appelé pendant l'attachement et le détachement de thread, mais le code d'exécution ne procède à aucune initialisation ni à aucun arrêt de sa propre initiative.  
  
## Que voulez\-vous faire ?  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)