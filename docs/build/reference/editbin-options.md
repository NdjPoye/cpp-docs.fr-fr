---
title: "Options EDITBIN | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "editbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EDITBIN, options du programme"
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Options EDITBIN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez y recourir pour modifier des fichiers objets, des fichiers exécutables et des bibliothèques de liens dynamiques \(DLLs\).  Les options indiquent les modifications qu'EDITBIN effectue.  
  
 Une option est constituée d'un spécificateur d'option, qui peut être un tiret \(–\) ou une barre oblique \(\/\) suivi\(e\) du nom de l'option.  Les noms des options ne peuvent pas être abrégés.  Certaines options acceptent des arguments qui sont spécifiés après le signe deux\-points \( : \).  Les espaces et les tabulations sont interdits dans la spécification d'une option.  Utilisez des espaces ou des tabulations pour séparer les spécifications des options sur la ligne de commande.  Les noms des options et leurs arguments \(mots clés ou noms de fichiers\) ne respectent pas la casse.  Par exemple, \-bind et \/BIND ont le même sens.  
  
 EDITBIN met en œuvre les options suivantes :  
  
|Option|Objectif|  
|------------|--------------|  
|[\/ALLOWBIND](../../build/reference/allowbind.md)|Spécifie si un DLL peut être lié.|  
|[\/ALLOWISOLATION](../../build/reference/allowisolation.md)|Spécifie la DLL ou le comportement manifeste de l'exécutable.|  
|[\/APPCONTAINER](../../build/reference/appcontainer.md)|Spécifie si l'application doit s'exécuter dans un appcontainer, par exemple un app [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].|  
|[\/BIND](../../build/reference/bind.md)|Définit les adresses des points d'entrée dans les objets spécifiés au moment du chargement de vitesse.|  
|[\/DYNAMICBASE](../../build/reference/dynamicbase.md)|Indique si la DLL peut être aléatoirement redéfinie au moment du chargement à l'aide de la fonctionnalité de randomisation de l'espace d'adresse \(ASLR\).|  
|[\/ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Signale les erreurs internes à Microsoft.|  
|[\/HEAP](../../build/reference/heap.md)|Définit la taille du segment exécutable de l'image en octets.|  
|[\/HIGHENTROPYVA](../../build/reference/highentropyva.md)|Spécifie si la DLL ou l'image exécutable prend en charge la randomisation du format d'espace d'adresse \(ASLR\) 64 bits de haute entropie.|  
|[\/INTEGRITYCHECK](../../build/reference/integritycheck.md)|Spécifie s'il faut vérifier la signature numérique lors du chargement.|  
|[\/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|Spécifie si l'objet prend en charge les adresses qui sont supérieures à deux gigaoctets.|  
|[\/NOLOGO](../../build/reference/nologo-editbin.md)|Supprime la bannière EDITBIN de démarrage.|  
|[\/NXCOMPAT](../../build/reference/nxcompat.md)|Spécifie si l'image exécutable est compatible avec la Prévention de l'exécution des données windows.|  
|[\/REBASE](../../build/reference/rebase.md)|Définit les adresses de base pour les objets spécifiés.|  
|[\/RELEASE](../../build/reference/release.md)|Définit le checksum dans l'en\-tête du fichier .exe.|  
|[\/SECTION](../../build/reference/section-editbin.md)|Substitue les attributs d'une section.|  
|[\/STACK](../../build/reference/stack.md)|Définit la taille de l'empilement exécutable de l'image en octets.|  
|[\/SUBSYSTEM](../../build/reference/subsystem.md)|Spécifie l'environnement d'exécution.|  
|[\/SWAPRUN](../../build/reference/swaprun.md)|Spécifie que l'image exécutable doit être copiée vers le fichier d'échange, puis exécute à partir de là.|  
|[\/TSAWARE](../../build/reference/tsaware.md)|Spécifie que l'application est conçue pour fonctionner dans un environnement multi\-utilisateur.|  
|[\/VERSION](../../build/reference/version.md)|Définit le numéro de version dans l'en\-tête.|  
  
## Voir aussi  
 [Outils de génération C\/C\+\+](../../build/reference/c-cpp-build-tools.md)   
 [Référence EDITBIN](../../build/reference/editbin-reference.md)