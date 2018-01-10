---
title: "Lier un exécutable à une DLL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- run time [C++], linking
- dynamic load linking [C++]
- linking [C++], DLLs
- DLLs [C++], linking
- implicit linking [C++]
- explicit linking [C++]
- executable files [C++], linking to DLLs
- loading DLLs [C++]
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6bdc8d4b372a589beb51d2f8a9bc05b1aa241c48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="link-an-executable-to-a-dll"></a>Lier un exécutable à une DLL  
  
Un fichier exécutable lié à (ou charge) une DLL de deux manières :  
  
-   *Liaison implicite*, où le système d’exploitation charge la DLL lors du chargement de l’exécutable de l’utiliser. L’exécutable client appelle les fonctions exportées de la DLL comme si les fonctions ont été statiquement liées et contenues dans le fichier exécutable. Liaison implicite est parfois appelée *charge statique* ou *la liaison dynamique au moment du chargement*.  
  
-   *Liaison explicite*, où le système d’exploitation charge la DLL à la demande lors de l’exécution. Un fichier exécutable qui utilise une DLL par liaison explicite doit effectuer des appels de fonction pour explicitement charger et décharger la DLL et d’accéder aux fonctions exportées par la DLL. Contrairement aux appels de fonctions dans une bibliothèque liée statiquement, l’exécutable client doit appeler les fonctions exportées dans une DLL via un pointeur de fonction. Liaison explicite est parfois appelée *charge dynamique* ou *liaison dynamique au moment de l’exécution*.  
  
Un fichier exécutable permet d’effectuer les deux méthodes de liaison à la même DLL. En outre, ces méthodes ne sont pas mutuellement exclusives ; un seul exécutable peut liaison implicite à une DLL et un autre peut attacher à celui-ci explicitement.  
  
<a name="determining-which-linking-method-to-use"></a>  
  
## <a name="determine-which-linking-method-to-use"></a>Déterminer la méthode de liaison à utiliser  
  
S’il faut utiliser la liaison implicite ou explicite de liaison est une décision architecturale, que vous devez effectuer pour votre application. Présente des avantages et inconvénients de chaque méthode.  
  
### <a name="implicit-linking"></a>Liaison implicite  
  
Liaison implicite se produit lorsqu’un code d’application appelle une fonction DLL exportée. Lorsque le code source pour l’exécutable appelant est compilé ou assemblé, l’appel de fonction DLL génère une référence de fonction externe dans le code objet. Pour résoudre cette référence externe, l’application doit être liée à la bibliothèque d’importation (fichier .lib) fournie par le créateur de la DLL.  
  
La bibliothèque d’importation contient uniquement le code pour charger la DLL pour implémenter les appels aux fonctions dans la DLL. Recherche d’une fonction externe dans une bibliothèque d’importation, l’éditeur de liens sont informe que le code de cette fonction se trouve dans une DLL. Pour résoudre les références externes aux DLL, l’éditeur de liens ajoute simplement des informations au fichier exécutable qui indique au système où trouver le code de la DLL lorsque le processus de démarrage.  
  
Lorsque le système démarre un programme qui contient des références liées dynamiquement, il utilise les informations dans le fichier exécutable du programme pour rechercher les DLL requises. S’il ne peut pas localiser la DLL, le système met fin au processus et affiche une boîte de dialogue qui signale l’erreur. Dans le cas contraire, le système mappe les modules de la DLL dans l’espace d’adressage du processus.  
  
Si l’une des DLL possède une fonction de point d’entrée pour le code d’initialisation et d’arrêt comme `DllMain`, le système d’exploitation appelle la fonction. Un des paramètres passés à la fonction de point d’entrée spécifie un code qui indique que la DLL est attaché au processus. Si la fonction de point d’entrée ne retourne pas la valeur TRUE, le système met fin au processus et signale l’erreur.  
  
Enfin, le système modifie le code exécutable du processus pour fournir des adresses de début pour les fonctions DLL.  
  
Comme le reste du code d’un programme, code de la DLL est mappé dans l’espace d’adressage du processus lorsque le processus démarre et s’il est chargé en mémoire uniquement lorsque nécessaire. Par conséquent, le `PRELOAD` et `LOADONCALL` les attributs de code utilisés par les fichiers .def pour contrôler le chargement dans les versions précédentes de Windows n’est plus ont.  
  
### <a name="explicit-linking"></a>Liaison explicite  
  
La plupart des applications utilisent la liaison implicite, car il s’agit de la méthode la plus simple de liaison à utiliser. Toutefois, il existe une liaison explicite est parfois nécessaire. Voici quelques raisons courantes pour utiliser la liaison explicite :  
  
-   L’application ne connaît pas le nom d’une DLL qu’il charge jusqu’au moment de l’exécution. Par exemple, l’application peut obtenir le nom de la DLL et les fonctions exportées à partir d’un fichier de configuration au démarrage.  
  
-   Un processus qui utilise la liaison implicite se termine par le système d’exploitation si la DLL est introuvable au démarrage du processus. Un processus qui utilise la liaison explicite n’est pas interrompu dans ce cas et peut tenter une récupération à partir de l’erreur. Par exemple, le processus peut avertir l’utilisateur de l’erreur et inviter l’utilisateur à spécifier un autre chemin d’accès à la DLL.  
  
-   Un processus qui utilise la liaison implicite est également interrompu si une des DLL auxquelles il est lié possède un `DllMain` fonction échoue. Un processus qui utilise la liaison explicite n’est pas interrompu dans ce cas.  
  
-   Une application liée de manière implicite à de nombreuses DLL peut être lente à démarrer car Windows charge toutes les DLL lors de la charge de l’application. Pour améliorer les performances de démarrage, une application peut lier implicitement uniquement pour les DLL requises immédiatement après le chargement et patientez jusqu'à ce que les autres DLL est requis pour les lier explicitement.  
  
-   Liaison explicite vous évite de lier l’application à l’aide d’une bibliothèque d’importation. Si les ordinaux d’exportation modifier les modifications apportées dans la DLL, les applications qui utilisent la liaison explicite est inutile d’associer de nouveau si elles appellent `GetProcAddress` en utilisant le nom d’une fonction et pas une valeur ordinale, tandis que les applications qui utilisent la liaison implicite doivent rétablir les liens à la nouvelle bibliothèque d’importation.  
  
Voici deux dangers de la liaison explicite à connaître :  
  
-   Si la DLL possède un `DllMain` fonction de point d’entrée, le système d’exploitation appelle la fonction dans le contexte du thread qui a appelé `LoadLibrary`. La fonction de point d’entrée n’est pas appelée si la DLL est déjà attachée au processus en raison d’un appel précédent à `LoadLibrary` qui a été sans appel correspondant à la `FreeLibrary` (fonction). Liaison explicite peut générer des problèmes si la DLL utilise une `DllMain` (fonction) pour effectuer l’initialisation de chaque thread d’un processus car les threads qui existent déjà lorsque `LoadLibrary` (ou `AfxLoadLibrary`) est appelé ne sont pas initialisés.  
  
-   Si une DLL déclare des données de portée statique en tant que `__declspec(thread)`, cela peut provoquer une erreur de protection si liée de manière explicite. Une fois que la DLL est chargée par un appel à `LoadLibrary`, elle provoque une erreur de protection chaque fois que le code fait référence à ces données. (Les données de portée statique incluent des éléments statiques globaux et locaux). Par conséquent, lorsque vous créez une DLL, vous devez éviter d’utiliser le stockage local des threads ou informer les utilisateurs des DLL les pièges potentiels du chargement dynamique de votre DLL. Pour plus d’informations, consultez [à l’aide du stockage local des threads dans une bibliothèque de liens dynamiques (SDK Windows)](http://msdn.microsoft.com/library/windows/desktop/ms686997).  
  
<a name="linking-implicitly"></a>  
  
## <a name="how-to-link-implicitly-to-a-dll"></a>Comment lier de manière implicite à une DLL  
  
Pour utiliser une DLL par la liaison implicite, les fichiers exécutables client doivent obtenir ces fichiers à partir du fournisseur de la DLL :  
  
-   Un ou plusieurs fichiers d’en-tête (fichiers .h) qui contiennent les déclarations des données exportées, des fonctions ou des classes C++ dans la DLL. Les classes, les fonctions et les données exportées par la DLL doivent tous être marquées `__declspec(dllimport)` dans le fichier d’en-tête. Pour plus d’informations, consultez [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
-   Une bibliothèque d’importation à lier dans votre fichier exécutable. L’éditeur de liens crée la bibliothèque d’importation lors de la DLL est générée. Pour plus d’informations, consultez [. Fichiers LIB](../build/reference/dot-lib-files-as-linker-input.md).  
  
-   Le fichier DLL réel.  
  
Pour utiliser une DLL par la liaison implicite, un fichier exécutable doit inclure les fichiers d’en-tête qui déclarent les données, les fonctions ou les classes C++ exportées par la DLL dans chaque fichier source qui contient des appels de fonctions, les données exportées et les classes. À partir d’une perspective de codage, les appels aux fonctions exportées sont comme n’importe quel autre appel de fonction.  
  
Pour générer le fichier exécutable appelant, vous devez lier avec la bibliothèque d’importation. Si vous utilisez un makefile externe ou le système de génération, spécifiez le nom de fichier de la bibliothèque d’importation listant d’autres fichiers objets (.obj) ou des bibliothèques que vous liez.  
  
Le système d’exploitation doit être en mesure de localiser le fichier DLL lors du chargement de l’exécutable appelant. Cela signifie que votre application doit déployer ou vérifier l’existence de la DLL lorsque votre application est installée.   
  
<a name="linking-explicitly"></a>  
  
## <a name="how-to-link-explicitly-to-a-dll"></a>Comment lier de manière explicite à une DLL  
  
Pour utiliser une DLL par liaison explicite, les applications doivent effectuer une appel de fonction pour charger explicitement la DLL au moment de l’exécution. Pour la liaison explicite à une DLL, une application doit :  
  
-   Appelez [LoadLibrary](loadlibrary-and-afxloadlibrary.md), `LoadLibraryEx`, ou une fonction similaire à charger la DLL et obtenir un handle de module.  
  
-   Appelez [GetProcAddress](getprocaddress.md) pour obtenir un pointeur de fonction à chaque fonction exportée qui appelle de l’application. Étant donné que les applications appellent les fonctions DLL via un pointeur, le compilateur ne génère pas de références externes, il est donc inutile de créer un lien avec une bibliothèque d’importation. Cependant, vous devez avoir un `typedef` ou `using` instruction qui définit la signature d’appel des fonctions exportées que vous appelez.   
  
-   Appelez [FreeLibrary](freelibrary-and-afxfreelibrary.md) quand vous avez terminé la DLL.  
  
Par exemple, cette fonction appelle `LoadLibrary` afin de charger une DLL nommée « MyDLL », les appels `GetProcAddress` pour obtenir un pointeur vers une fonction nommée « DLLFunc1 », appelle la fonction et enregistre le résultat et puis appelle `FreeLibrary` pour décharger la DLL. 
  
```C  
#include "windows.h"

typedef HRESULT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT*);  

HRESULT LoadAndCallSomeFunction(DWORD dwParam1, UINT * puParam2)  
{
    HINSTANCE hDLL;               // Handle to DLL  
    LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
    HRESULT hrReturnVal;  
      
    hDLL = LoadLibrary("MyDLL");  
    if (NULL != hDLL)  
    {  
        lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL, "DLLFunc1");  
        if (NULL != lpfnDllFunc1)  
        {  
            // call the function  
            hrReturnVal = lpfnDllFunc1(dwParam1, puParam2);  
        }  
        else  
        {  
            // report the error  
            hrReturnVal = ERROR_DELAY_LOAD_FAILED;  
        }
        FreeLibrary(hDLL);
    }
    else
    {
        hrReturnVal = ERROR_DELAY_LOAD_FAILED;
    }  
    return hrReturnVal;
}
```  
  
Contrairement à dans cet exemple, dans la plupart des cas vous devez appeler `LoadLibrary` et `FreeLibrary` qu’une seule fois dans votre application pour une DLL donnée, en particulier si vous vous apprêtez à appeler plusieurs fonctions dans la DLL ou DLL fonctionne à plusieurs reprises.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation de bibliothèques d’importation et de fichiers d’exportation](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [Le chemin de recherche utilisé par Windows pour retrouver une DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## <a name="see-also"></a>Voir aussi  
 [DLL dans Visual C++](../build/dlls-in-visual-cpp.md)