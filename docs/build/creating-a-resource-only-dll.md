---
title: "Cr&#233;ation d&#39;une DLL de ressource uniquement | Microsoft Docs"
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
  - "DLL (C++), créer"
  - "DLL de ressources uniquement (C++), créer"
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Cr&#233;ation d&#39;une DLL de ressource uniquement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une DLL de ressource uniquement est une DLL qui ne contient que des ressources, telles que des icônes, des images bitmap, des chaînes et des boîtes de dialogue.  L'utilisation d'une DLL de ressource uniquement est une bonne méthode pour partager le même jeu de ressources entre plusieurs programmes.  C'est aussi une bonne manière de doter une application de ressources localisées pour plusieurs langues \(consultez [Ressources localisées dans des applications MFC : DLL satellites](../build/localized-resources-in-mfc-applications-satellite-dlls.md)\).  
  
 Pour créer une DLL de ressource uniquement, créez un nouveau projet de DLL Win32 \(non\-MFC\) et ajoutez\-y vos ressources.  
  
-   Sélectionnez Projet Win32 dans la boîte de dialogue **Nouveau projet** et spécifiez un type de projet DLL dans l'Assistant Projet Win32.  
  
-   Créez un script de ressource contenant les ressources \(une chaîne ou un menu, par exemple\) de la DLL et enregistrez le fichier .rc.  
  
-   Dans le menu **Projet**, cliquez sur **Ajouter un élément existant** et insérez le nouveau fichier .rc dans le projet.  
  
-   Spécifiez l'option [\/NOENTRY](../build/reference/noentry-no-entry-point.md) de l'éditeur de liens. \/NOENTRY empêche l'éditeur de liens de lier à la DLL une référence désignant \_main ; cette option est requise pour la création d'une DLL de ressource uniquement.  
  
-   Générez la DLL.  
  
 L'application qui utilise la DLL de ressource uniquement doit appeler **LoadLibrary** pour se [lier de manière explicite à la DLL](../build/loadlibrary-and-afxloadlibrary.md).  Pour accéder aux ressources, appelez les fonctions génériques **FindResource** et **LoadResource**, qui fonctionnent sur n'importe quel type de ressources, ou appelez l'une des fonctions spécifiques aux ressources suivantes :  
  
-   `FormatMessage`  
  
-   **LoadAccelerators**  
  
-   `LoadBitmap`  
  
-   `LoadCursor`  
  
-   `LoadIcon`  
  
-   `LoadMenu`  
  
-   `LoadString`  
  
 L'application doit appeler **FreeLibrary** quand elle a fini d'utiliser les ressources.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [DELETE\_PENDING\_Editing Resources](http://msdn.microsoft.com/fr-fr/c29d31c7-2d94-40ca-8aa0-c7262883529c)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)