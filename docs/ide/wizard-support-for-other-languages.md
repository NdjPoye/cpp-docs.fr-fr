---
title: "Prise en charge de l’Assistant pour d’autres langues | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.EastAsianLanguages
dev_langs:
- C++
helpviewer_keywords:
- wizards [C++], language support
- language support for MFC projects
- projects [C++], language support
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef95c252621aa7f725098dfcd08c7b5b3620826
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="wizard-support-for-other-languages"></a>Prise en charge d'autres langues par l'Assistant
Lorsque vous installez Visual Studio, le programme d’installation détecte les paramètres régionaux installé sur votre système et installe les modèles pour ces paramètres régionaux ou un modèle de langage approprié. Par exemple, pour les paramètres régionaux européens occidentales, le programme d’installation installe anglais, Français, italien, espagnol et allemand. Ces langues figurent dans le **langue de ressource** liste sur le [Type d’Application](../mfc/reference/application-type-mfc-application-wizard.md) page de l’Assistant Application MFC.  
  
## <a name="language-templates"></a>Modèles de langue  
 Pas de tous les modèles sont installés sur tous les systèmes, car les modèles sont ANSI encodage, et pas toutes les ressources peuvent être modifiées sur tous les systèmes. Par exemple, par défaut, vous ne pouvez pas modifier des ressources de langue japonaise sur un système Français.  
  
 Si vous utilisez Windows 2000 ou version ultérieure et que vous souhaitez créer une application MFC dans une autre langue, vous devez copier le répertoire de modèles pour la langue appropriée à partir du support d’installation de Visual Studio (disque 1) sur votre système.  
  
> [!NOTE]
>  Pour modifier le projet créé, vous devez définir les paramètres régionaux système pour les paramètres régionaux appropriés pour la langue sélectionnée.  
  
 Les modèles sont chacun ayant un dossier dans le répertoire \Microsoft Visual Studio .NET 2003\Vc7\VCWizards\mfcappwiz\templates\, comme indiqué dans le tableau suivant. Pour accéder au modèle de langue de votre choix, copiez le dossier approprié dans le répertoire \mfcappwiz\templates\ sur votre ordinateur. Une fois que vous avez copié le dossier, la langue apparaît dans le **langue de ressource** liste sur le **Type d’Application** page de l’Assistant Application MFC.  
  
### <a name="language-templates-provided-in-visual-studio-net"></a>Modèles de langue fournis dans Visual Studio .NET  
  
|Langue|Modèle|  
|--------------|--------------|  
|Chinois (traditionnel)|1028|  
|Chinois (simplifié)|2052|  
|Anglais|1033|  
|Français|1036|  
|Allemand|1031|  
|Italien|1040|  
|Japonais|1041|  
|Coréen|1042|  
|Espagnol|3082|  
  
## <a name="format-of-visual-c-wizard-generated-files"></a>Format des fichiers générés par l’Assistant de C++ de Visual  
 Les Assistants Visual C++ génère les projets au format Unicode lors de la version linguistique installée de Visual Studio ne correspond pas à la langue du système. Par exemple, lorsque la version japonaise de Visual Studio est installée sur un ordinateur qui a des paramètres régionaux définis pour une autre langue, les Assistants Visual C++ génère projets composés de fichiers Unicode. Cela est courant sur les ordinateurs à configurer avec les packs de Windows multilingues (MUI).  
  
 Ce comportement diffère des systèmes tels que les paramètres régionaux système sont identique à la version linguistique de Visual Studio. Dans ce cas, les fichiers projet seront créés au format ANSI dans la page de codes du système.  
  
## <a name="see-also"></a>Voir aussi  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Création et gestion de projets Visual C++](../ide/creating-and-managing-visual-cpp-projects.md)