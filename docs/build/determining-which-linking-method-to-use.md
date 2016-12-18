---
title: "M&#233;thode de liaison &#224; utiliser | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "liaison explicite (C++)"
  - "liaison implicite (C++)"
ms.assetid: 6b6d3fec-4711-4a30-af5b-354b965ecaec
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# M&#233;thode de liaison &#224; utiliser
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe deux types de liaison : la liaison implicite et la liaison explicite.  
  
## Liaison implicite  
 La [liaison implicite](../build/linking-implicitly.md) est mise en œuvre quand un code d'application appelle une fonction de la DLL exportée.  Quand le code source de l'exécutable appelant est compilé ou assemblé, l'appel de la fonction de la DLL génère une référence de fonction externe dans le code objet.  Pour résoudre cette référence externe, l'application doit être liée à la bibliothèque d'importation \(fichier .lib\) fournie par l'auteur de la DLL.  
  
 La bibliothèque d'importation contient uniquement le code de chargement de la DLL et d'implémentation d'appels aux fonctions de la DLL.  Quand une fonction externe est retrouvée dans une bibliothèque d'importation, l'éditeur de liens détermine alors que le code de cette fonction se trouve dans une DLL.  Pour résoudre les références externes aux DLL, l'éditeur de liens ajoute simplement des informations au fichier exécutable pour indiquer au système où trouver le code de la DLL au démarrage du processus.  
  
 Quand le système lance un programme contenant des références liées de manière dynamique, il reprend les informations du fichier exécutable du programme pour rechercher les DLL requises.  S'il ne retrouve pas les DLL, le système interrompt le processus et affiche une boîte de dialogue indiquant l'erreur.  Sinon, le système mappe les modules de la DLL dans l'espace d'adressage du processus.  
  
 Si l'une des DLL possède une fonction de point d'entrée \(pour le code d'initialisation et d'arrêt\), le système d'exploitation appelle cette fonction.  L'un des paramètres passés à la fonction de point d'entrée spécifie un code qui indique que la DLL s'attache au processus.  Si la fonction de point d'entrée ne retourne pas la valeur TRUE, le système arrête le processus et signale l'erreur.  
  
 Enfin, le système modifie le code exécutable du processus afin de fournir des adresses de départ pour les fonctions de la DLL.  
  
 Comme le reste du code d'un programme, le code de la DLL est mappé dans l'espace d'adressage du processus au démarrage de celui\-ci et est chargé en mémoire uniquement en cas de besoin.  De ce fait, les attributs de code **PRELOAD** et **LOADONCALL** utilisés par les fichiers .def pour contrôler le chargement dans les versions précédentes de Windows n'ont plus de raison d'être.  
  
## Liaison explicite  
 La plupart des applications utilisent la liaison implicite car c'est la méthode de liaison la plus simple à adopter.  Cependant, la [liaison explicite](../build/linking-explicitly.md) est parfois nécessaire.  Voici quelques raisons courantes qui justifient l'utilisation de la liaison explicite :  
  
-   L'application ne découvre le nom d'une DLL qu'elle doit charger qu'au moment de l'exécution.  Par exemple, l'application peut avoir besoin d'obtenir le nom de la DLL et des fonctions exportées à partir d'un fichier de configuration.  
  
-   Un processus utilisant la liaison implicite est interrompu par le système d'exploitation si la DLL est introuvable au moment du démarrage du processus.  Un processus utilisant la liaison explicite n'est pas interrompu dans ce cas et peut essayer de récupérer à partir de l'erreur.  Par exemple, le processus peut signaler l'erreur à l'utilisateur et lui demander de spécifier un autre chemin d'accès de la DLL.  
  
-   Un processus qui utilise la liaison implicite est également interrompu si l'une des DLL auxquelles il est lié possède une fonction `DllMain` qui échoue.  Un processus utilisant la liaison explicite n'est pas interrompu dans ce cas.  
  
-   Une application liée de manière implicite à de nombreuses DLL peut être lente à démarrer car Windows charge toutes les DLL en même temps que l'application.  Pour accélérer le démarrage, une application peut être liée de manière implicite aux DLL requises immédiatement après le chargement, puis attendre d'être liée explicitement aux autres DLL au fur et à mesure des besoins.  
  
-   Avec la liaison explicite, il n'est plus nécessaire de lier l'application à une bibliothèque d'importation.  Si les ordinaux d'exportation changent à la suite de modifications apportées à la DLL, les applications utilisant la liaison explicite n'ont pas besoin d'être rééditées \(à supposer qu'elles appellent **GetProcAddress** à l'aide d'un nom de fonction et non avec une valeur ordinale\), alors que les applications utilisant la liaison implicite doivent subir une réédition de leurs liens avec la nouvelle bibliothèque d'importation.  
  
 Voici deux dangers de la liaison explicite auxquels il faut faire attention :  
  
-   Si la DLL possède une fonction de point d'entrée `DllMain`, le système d'exploitation appelle la fonction dans le contexte du thread ayant appelé **LoadLibrary**.  La fonction de point d'entrée n'est pas appelée si la DLL est déjà attachée au processus à la suite d'un appel précédent à **LoadLibrary** sans appel correspondant à la fonction **FreeLibrary**.  La liaison explicite peut générer des problèmes si la DLL utilise une fonction `DllMain` pour réaliser l'initialisation de chaque thread d'un processus car les threads existant au moment où la fonction **LoadLibrary** \(ou `AfxLoadLibrary`\) est appelée ne peuvent pas être initialisés.  
  
-   Si une DLL déclare des données de portée statique en tant que **\_\_declspec\(thread\)**, elle peut déclencher une erreur de protection en cas de liaison explicite.  Une fois la DLL chargée à l'aide de la fonction **LoadLibrary**, elle provoque une erreur de protection chaque fois que le code fait référence à ces données. \(Les données de portée statique incluent les éléments statiques à la fois locaux et globaux.\) Par conséquent, lorsque vous créez une DLL, vous devez soit éviter d'utiliser le stockage local des threads soit informer les utilisateurs des DLL des risques potentiels qu'ils encourent \(au cas où ils tenteraient un chargement dynamique\).  
  
## Que voulez\-vous faire ?  
  
-   [Lier de manière implicite](../build/linking-implicitly.md)  
  
-   [Lier de manière explicite](../build/linking-explicitly.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Chemin de recherche utilisé par Windows pour retrouver une DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [LoadLibrary et AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
-   [FreeLibrary et AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [\<caps:sentence id\="tgt47" sentenceid\="8081a197f9413cac12a30b57c2612af5" class\="tgtSentence"\>Utilisation du stockage local des threads dans une bibliothèque de liens dynamiques \(Kit de développement logiciel Windows\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms686997)  
  
## Voir aussi  
 [Liaison d'un exécutable à une DLL](../build/linking-an-executable-to-a-dll.md)