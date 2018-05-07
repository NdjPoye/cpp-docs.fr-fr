---
title: Pages de propriétés de l’éditeur de liens | Documents Microsoft
ms.custom: ''
ms.date: 11/21/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
dev_langs:
- C++
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cec232bb4e4f2f6ac1ab9af703b368eec0ba5dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-property-pages"></a>pages de propriétés de l'Éditeur de liens

Cette rubrique décrit les propriétés suivantes sur le **général** page de propriétés de l’éditeur de liens. Pour la version Linux de cette page, consultez [propriétés de l’éditeur de liens (C++ Linux)](../linux/prop-pages/linker-linux.md).

## <a name="general-page-properties"></a>Propriétés de la page Général

### <a name="ignore-import-library"></a>Bibliothèque d’importation ignorée

Cette propriété indique à l’éditeur de liens ne pas lier de sortie .lib généré à partir de cette génération dans n’importe quel projet dépendant. Ainsi, le système de projet gérer les fichiers .dll qui ne produisent pas un fichier .lib lors de la génération. Si un projet dépend d’un autre projet qui produit une DLL, le système de projet lie automatiquement le fichier .lib produit par ce projet enfant. Cela ne peut pas être nécessaire par les projets qui produisent des DLL COM ou des DLL de ressource uniquement ; Ces DLL n’ont pas d’exportation significative. Si une DLL n’a aucune exportation, l’éditeur de liens ne génère pas un fichier .lib. Si aucun fichier .lib d’exportation n’est présent sur le disque et le système de projet indique à l’éditeur de liens à lier à cette DLL (manquante), la liaison échoue. Utilisez le **bibliothèque d’importation ignorée** propriété pour résoudre ce problème. Lorsque la valeur **Oui**, le système de projet ignore la présence ou l’absence de ce fichier .lib et entraîne un projet dépendant de ce projet ne pas de liaison avec le fichier .lib.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>.

### <a name="register-output"></a>Inscription de la sortie

S’exécute `regsvr32.exe /s $(TargetPath)` sur la sortie de génération, qui n’est valide uniquement sur les projets .dll. Pour les projets .exe, cette propriété est ignorée. Pour enregistrer un fichier de sortie .exe, définissez un événement post-build dans la configuration à effectuer l’inscription personnalisée qui est toujours requise pour les fichiers .exe inscrits.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>.

### <a name="per-user-redirection"></a>Redirection par utilisateur

L’inscription dans Visual Studio a effectue traditionnellement dans HKEY_CLASSES_ROOT (HKCR). Avec Windows Vista et les systèmes d’exploitation ultérieurs, pour accéder à HKCR vous devez exécuter Visual Studio en mode élevé. Les développeurs ne souhaitent pas toujours s’exécuter en mode élevé mais toujours doivent s’inscrire. Redirection par utilisateur vous permet de vous inscrire sans avoir à exécuter dans ce mode.

Redirection par utilisateur force toutes les écritures dans HKCR à être redirigées vers HKEY\_actuel\_utilisateur (HKCU). Si la redirection par utilisateur est désactivée, cela peut provoquer [Project Build Error PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) lorsque le programme tente d’écrire dans HKCR.

### <a name="link-library-dependencies"></a>Lier les dépendances de la bibliothèque

Spécifie s’il faut lier les fichiers .lib produits par les projets dépendants. En règle générale, vous souhaitez lier les fichiers .lib, mais cela ne peut pas être le cas pour certains fichiers DLL.

Vous pouvez également spécifier un fichier .obj par en fournissant le nom de fichier et le chemin d’accès relatif, par exemple «.. \\.. \MyLibProject\MyObjFile.obj ». Si la source du code pour le fichier .obj #includes un en-tête précompilé pch.h par exemple, le fichier pch.obj se trouve dans le même dossier que MyObjFile.obj, et vous devez également ajouter pch.obj en tant que dépendance supplémentaire.

### <a name="use-library-dependency-inputs"></a>Utiliser les entrées de dépendance de la bibliothèque

Dans un grand projet, lorsqu’un projet dépendant produit un fichier .lib, liaison incrémentielle est désactivée. S’il existe plusieurs projets dépendants qui génèrent des fichiers .lib, la génération de l’application peut prendre un certain temps. Lorsque cette propriété a la valeur **Oui**, le système de projet lie les fichiers .obj de .libs produits par les projets dépendants, activant ainsi la liaison incrémentielle.

Pour plus d’informations sur l’accès à la **général** page de propriétés de l’éditeur de liens, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).

## <a name="see-also"></a>Voir aussi

[Paramètres du projet VC++, Projets et solutions, boîte de dialogue Options](/visualstudio/ide/reference/vcpp-project-settings-projects-and-solutions-options-dialog-box)  
[Pages de propriétés](../ide/property-pages-visual-cpp.md)  