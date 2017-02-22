---
title: "Pages de propri&#233;t&#233;s de l&#39;&#201;diteur de liens | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.RegisterOutput"
  - "VC.Project.VCLinkerTool.IgnoreImportLibrary"
  - "VC.Project.VCLinkerTool.UseLibraryDependencyInputs"
  - "VC.Project.VCLinkerTool.LinkLibraryDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "redirection par utilisateur"
  - "pages de propriétés de l'Éditeur de liens"
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Pages de propri&#233;t&#233;s de l&#39;&#201;diteur de liens
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit les propriétés suivantes de la page de propriétés **Général** de l'Éditeur de liens :  
  
 **Bibliothèque d'importation ignorée**  
 Indique à l'Éditeur de liens de ne pas tenter de lier de fichier .lib créé à partir de cette génération dans n'importe quel projet dépendant.  Vous autorisez ainsi le système de projet à gérer les fichiers .dll qui ne créent pas de fichier .lib lors de la génération.  Si un projet dépend d'un autre projet créant une DLL, le système de projet lie automatiquement le fichier .lib produit par ce projet enfant.  Il se peut que cette option ne soit pas nécessaire pour les projets créant des DLL COM ou des DLL de ressource uniquement. En effet, ces DLL ne possèdent pas d'exportation significative.  Si une DLL ne possède aucune exportation, l'Éditeur de liens ne crée pas de fichier .lib.  Si aucun fichier .lib d'exportation n'est présent sur le disque et si le système de projet indique à l'Éditeur de liens d'effectuer la liaison à cette DLL \(manquante\), la liaison échoue.  
  
 Utilisez l'option **Bibliothèque d'importation ignorée** pour résoudre ce problème.  Si elle a la valeur `Yes`, le système de projet ignore la présence ou l'absence de ce fichier .lib et empêche la liaison d'un projet dépendant de ce projet avec le fichier .lib manquant.  
  
 Pour accéder par programme à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>.  
  
 **Inscription de la sortie**  
 Exécute regsvr32.exe \/s $\(TargetPath\), qui est valide uniquement sur les projets .dll.  Pour les projets .exe, cette propriété est ignorée.  Si vous souhaitez inscrire un fichier de sortie .exe, définissez un événement post\-build dans la configuration afin d'effectuer l'inscription personnalisée obligatoire pour les fichiers .exe inscrits.  
  
 Pour accéder par programme à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>.  
  
 **Redirection par utilisateur**  
 L'inscription dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] s'effectue traditionnellement dans HKEY\_CLASSES\_ROOT \(HKCR\).  Avec [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)], pour accéder à HKCR vous devez exécuter [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] en mode élevé.  Les développeurs ne souhaitent pas toujours exécuter l'application en mode élevé mais sont toujours obligés de s'inscrire.  La redirection par utilisateur vous permet de vous inscrire sans avoir à exécuter ce mode.  
  
 La redirection par utilisateur forcera toutes les écritures dans HKCR à être redirigées vers HKEY\_CURRENT\_USER \(HKCU\).  Si la redirection par utilisateur est désactivée, cela peut provoquer [Erreur de génération de projet PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) lorsque le programme essaie d'écrire dans HKCR.  
  
 **Dépendances de bibliothèque de liens**  
 Permet de lier les fichiers .lib qui sont produits par les projets dépendants.  En général, vous souhaiterez lier le fichier .lib.  
  
 Vous pouvez également spécifier un fichier .obj en fournissant le nom du fichier et le chemin d'accès relatif, par exemple **..\\..\\MyLibProject\\MyObjFile.obj**.  Si le code source du fichier .obj des \#inclue un en\-tête précompilé, par exemple pch.h, alors le fichier pch.obj est situé dans le même dossier que **MyObjFile.obj** et vous devez également ajouter **pch.obj** comme dépendance supplémentaire.  
  
 **Utiliser les entrées de dépendance de bibliothèque**  
 Dans un grand projet, lorsqu'un projet dépendant produit un fichier .lib, la liaison incrémentielle est désactivée.  S'il existe plusieurs projets dépendants qui génèrent des fichiers .lib, la génération de l'application peut prendre un certain temps.  Lorsque cette propriété a la valeur `Yes`, le système de projet lie les fichiers .obj des fichiers .libs produits par les projets dépendants, activant ainsi la liaison incrémentielle.  
  
 Pour plus d'informations sur l'accès à la page de propriétés **Général**, consultez [Comment : spécifier des propriétés de projet avec des pages de propriétés](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
## Voir aussi  
 [VC\+\+ Directories, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/fr-fr/e027448b-c811-4c3d-8531-4325ad3f6e02)   
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)