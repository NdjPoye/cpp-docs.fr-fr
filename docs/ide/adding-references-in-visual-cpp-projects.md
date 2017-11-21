---
title: "Ajouter des références de projets Visual C++ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.References
dev_langs: C++
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7aacc70a74b7c7fccb66a0a8363a261f4a8f1ba3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-references-in-visual-c-projects"></a>Ajout de références aux projets Visual C++
Il est très courant pour les programmes d’appeler des API dans d’autres fichiers binaires comme les DLL, les composants Windows Runtime, les Kits de développement logiciel (SDK) d’extension, les composants COM et les assemblys .NET. La façon dont votre programme détecte les autres fichiers binaires dépend de votre type de projet et du type de fichier binaire.  
  
 Dans un projet C++ natif, si vous consommez une DLL ou un composant COM natif qui n’est pas produit par un autre projet de votre solution, utilisez LoadLibrary ou CoCreateInstance pour spécifier le chemin du fichier binaire. Sinon, laissez le système le rechercher à des emplacements spécifiques bien définis.  
  
 Dans d’autres types de projet tels que les projets UWP ou C++/CLI, ou quand le fichier binaire est produit par un autre projet de votre solution, vous ajoutez une *référence* à l’assembly, au composant ou au projet.   Une référence est essentiellement un ensemble de données qui permet à votre programme de localiser l’emplacement du fichier binaire, et de communiquer avec ce dernier.       Quand vous ajoutez une référence, Visual Studio gère les détails de bas niveau. Pour définir les références d’un projet C++ pour .NET Frameworkassemblies (C + c++ / CLI uniquement), des composants COM, les autres projets dans votre solution, notamment les projets partagés ou les services connectés, avec le bouton droit sur le **références** nœud **L’Explorateur de solutions** pour afficher les **Gestionnaire de références**. Ce que vous voyez dans le Gestionnaire de références diffère selon le type de votre projet.  
  
 Dans un projet C++ natif (ATL), le concept de *références* s’applique uniquement aux autres projets de la solution, notamment les projets partagés. Ainsi, vous ne voyez que cela dans le **Gestionnaire de références**:  
  
 ![Visual C &#43; &#43; Gestionnaire de références &#40; Projets ATL &#41; ] (../ide/media/visual-c---reference-manager--atl-projects-.png "Du Gestionnaire de références visual C++ (projets ATL)")  
  
 Dans un projet C++/CLI ou un projet de plateforme Windows universelle, le concept de références s’applique à plusieurs genres de fichiers binaires, en plus des autres projets de la solution.  Ceux-ci sont tous exposés dans le **Gestionnaire de références**.
  
## <a name="reference-properties"></a>Propriétés de référence  
 Chaque genre de référence possède des propriétés. Pour afficher les propriétés, sélectionnez la référence dans l’Explorateur de solutions et appuyez sur **Alt+Entrée**, ou cliquez avec le bouton droit et choisissez **Propriétés**. Certaines propriétés sont en lecture seule, et d’autres peuvent être modifiées. Toutefois, en règle générale, vous n’avez pas à modifier ces propriétés manuellement.  
  
### <a name="activex-reference-properties"></a>Propriétés de référence ActiveX  
 Les propriétés de référence ActiveX sont disponibles uniquement pour les références aux composants COM. Ces propriétés sont affichées uniquement quand un composant COM est sélectionné dans le volet **Références** . Les propriétés ne peuvent pas être modifiées.  
  
 **Chemin d’accès complet du contrôle**  
 Affiche le chemin d'accès du répertoire du contrôle référencé.  
  
 **GUID du contrôle**  
 Affiche le GUID du contrôle ActiveX.  
  
 **Version de contrôle**  
 Affiche la version du contrôle ActiveX référencé.  
  
 **Nom de la bibliothèque de types**  
 Affiche le nom de la bibliothèque de types référencée.  
  
 **Outil wrapper**  
 Affiche l'outil utilisé pour générer l'assembly d'interopérabilité à partir de la bibliothèque COM référencée ou d'un contrôle ActiveX.  
  
### <a name="assembly-reference-properties"></a>Propriétés de la référence à l'assembly  
 Propriétés de référence d’assembly sont disponibles uniquement pour les références à Frameworkassemblies .NET dans C + c++ / projets CLI. Ces propriétés sont affichées uniquement lorsqu’un Frameworkassembly .NET est sélectionné dans le **références** volet. Les propriétés ne peuvent pas être modifiées.  
  
 **Chemin d’accès relatif**  
 Affiche le chemin d'accès relatif du répertoire de projet à l'assembly référencé.  
  
### <a name="build-properties"></a>Propriétés de build  
 Les propriétés suivantes sont disponibles sur divers genres de références. Elles vous permettent de spécifier le mode de génération avec des références.  
  
 **Copie locale**  
 Spécifie si l'assembly référencé doit être copié automatiquement vers l'emplacement cible pendant une génération.  
  
 **Copier les assemblys satellites locaux**  
 Spécifie si les assemblys satellites de l'assembly référencé doivent être copiés automatiquement vers l'emplacement cible pendant une génération. Utilisé uniquement si **Copie locale** a la valeur `true`.  
  
 **Sortie de l’assembly de référence**  
 Spécifie que cet assembly est utilisé dans le processus de génération. Si la valeur est `true`, l'assembly est utilisé sur la ligne de commande du compilateur durant la génération.  
  
### <a name="project-to-project-reference-properties"></a>Propriétés de référence entre projets  
 Les propriétés suivantes définissent une *référence entre projets* , depuis le projet sélectionné dans le volet **Références** vers un autre projet dans la même solution. Pour plus d’informations, consultez [Gestion des références dans un projet](/visualstudio/ide/managing-references-in-a-project).  
  
 **Lier les dépendances de la bibliothèque**  
 Quand cette propriété a la valeur **True**, le système de projet lie au projet dépendant les fichiers .lib produits par le projet indépendant. En général, vous devez spécifier **True**.  
  
 **Identificateur de projet**  
 Identifie de façon unique le projet indépendant. La valeur de propriété est un GUID système interne qui ne peut pas être modifié.  
  
 **Utiliser les entrées de dépendance de la bibliothèque**  
 Quand cette propriété a la valeur **False**, le système de projet ne lie pas au projet dépendant les fichiers .obj de la bibliothèque produite par le projet indépendant. Ainsi, cette valeur désactive la liaison incrémentielle. En général, vous spécifiez **False** , car la génération de l'application peut prendre du temps, s'il existe de nombreux projets indépendants.  
  
### <a name="reference-properties"></a>Propriétés de référence  
 Les propriétés suivantes font partie des références d’assembly COM et .NET. Elles ne peuvent pas être modifiées.  
  
 **Nom de l'assembly**  
 Affiche le nom de l'assembly pour l'assembly référencé.  
  
 **Culture**  
 Affiche la culture de la référence sélectionnée.  
  
 **Description**  
 Affiche la description de la référence sélectionnée.  
  
 **Chemin d'accès complet**  
 Affiche le chemin d'accès du répertoire de l'assembly référencé.  
  
 **Identité**  
 Pour le Frameworkassemblies .NET, affiche le chemin d’accès complet. Pour les composants COM, affiche le GUID.  
  
 **Étiquette**  
 Affiche l'étiquette de la référence.  
  
 **Nom**  
 Affiche le nom de la référence.  
  
 **Jeton de clé publique**  
 Affiche le jeton de clé publique utilisé pour identifier l'assembly référencé.  
  
 **Nom fort**  
 `true` si l'assembly référencé a un nom fort. Un assembly à nom fort est associé à une version unique.  
  
 **Version**  
 Affiche la version de l'assembly référencé.  
  
## <a name="see-also"></a>Voir aussi  
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)   
 [Utilisation des propriétés de projet](../ide/working-with-project-properties.md)