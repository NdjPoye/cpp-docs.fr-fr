---
title: "Erreur des outils &#201;diteur de liens LNK1123 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1123"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1123"
ms.assetid: fe47af69-0f42-4792-9133-541192cd8514
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1123
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

échec lors de la conversion en fichier COFF : fichier non valide ou endommagé  
  
 Les fichiers d'entrée doivent avoir le format COFF \(Common Object File Format\).  Si un fichier d'entrée n'est pas au format COFF, l'éditeur de liens essaie automatiquement de convertir les objets OMF 32 bits au format COFF, ou exécute CVTRES.EXE pour convertir les fichiers de ressources.  Ce message indique que l'éditeur de liens n'a pas pu convertir le fichier.  Cela peut également se produire lors de l'utilisation d'une version incompatible de CVTRES.EXE à partir d'une autre installation de Visual Studio, du Kit de développement Windows ou du .NET Framework.  
  
> [!NOTE]
>  Si vous exécutez une version antérieure de Visual Studio, il est possible que la conversion automatique ne soit pas prise en charge.  
  
### Pour corriger ce problème  
  
-   Appliquez l'ensemble des service packs et des mises à jour pour votre version de Visual Studio.  Ceci est particulièrement important pour Visual Studio 2010.  
  
-   Tentez une génération après avoir désactivé les liens incrémentiels.  Dans la barre de menus, choisissez **Projet**, **Propriétés**.  Dans la boîte de dialogue **Pages de propriétés**, développez **Propriétés de configuration**, **Éditeur de liens**.  Faites passer la valeur de **Activation des liens incrémentiels** à **Non**.  
  
-   Vérifiez que la version de CVTRES.EXE trouvée en premier dans votre variable d'environnement PATH correspond à la version des outils de génération ou à la version de l'Ensemble d'outils de plateforme, utilisée par votre projet.  
  
-   Essayez de désactiver l'option Incorporer le manifeste.  Dans la barre de menus, choisissez **Projet**, **Propriétés**.  Dans la boîte de dialogue **Pages de propriétés**, développez **Propriétés de configuration**, **Outil manifeste**, **Entrée et sortie**.  Affectez à **Incorporer le manifeste** la valeur **Non**.  
  
-   Assurez\-vous que le type de fichier est valide.  Par exemple, assurez\-vous qu'un objet OMF est un objet 32 bits et non pas 16 bits.  Pour plus d'informations, consultez [Fichiers .obj en tant qu'entrée de l'Éditeur de liens](../../build/reference/dot-obj-files-as-linker-input.md) et [Spécification Microsoft PE et COFF](http://go.microsoft.com/fwlink/p/?LinkId=93292).  
  
-   Assurez\-vous que le fichier n'est pas endommagé.  Régénérez\-le, si nécessaire.  
  
## Voir aussi  
 [Fichiers .obj en tant qu'entrée de l'Éditeur de liens](../../build/reference/dot-obj-files-as-linker-input.md)   
 [Référence EDITBIN](../../build/reference/editbin-reference.md)   
 [Référence DUMPBIN](../../build/reference/dumpbin-reference.md)