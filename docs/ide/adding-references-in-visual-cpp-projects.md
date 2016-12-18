---
title: "Ajout de r&#233;f&#233;rences aux projets Visual&#160;C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.References"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework (C++), Ajouter des références (boîte de dialogue)"
  - "Ajouter des références (boîte de dialogue C++)"
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout de r&#233;f&#233;rences aux projets Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il est très courant pour les programmes d’appeler des API dans d’autres fichiers binaires comme les DLL, les composants Windows Runtime, les Kits de développement logiciel \(SDK\) d’extension, les composants COM et les assemblys .NET. La façon dont votre programme détecte les autres fichiers binaires dépend de votre type de projet et du type de fichier binaire.  
  
 Dans un projet C\+\+ natif, si vous consommez une DLL ou un composant COM natif qui n’est pas produit par un autre projet de votre solution, utilisez LoadLibrary ou CoCreateInstance pour spécifier le chemin du fichier binaire. Sinon, laissez le système le rechercher à des emplacements spécifiques bien définis.  
  
 Dans d’autres types de projet tels que les projets UWP ou C\+\+\/CLI, ou quand le fichier binaire est produit par un autre projet de votre solution, vous ajoutez une *référence* à l’assembly, au composant ou au projet.   Une référence est essentiellement un ensemble de données qui permet à votre programme de localiser l’emplacement du fichier binaire, et de communiquer avec ce dernier.       Quand vous ajoutez une référence, Visual Studio gère les détails de bas niveau. Pour définir les références d’un projet C\+\+ à des assemblys [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] \(C\+\+\/CLI uniquement\), des composants COM ou d’autres projets de votre solution, notamment les projets partagés ou les services connectés, cliquez avec le bouton droit sur le nœud **Références** dans l’**Explorateur de solutions** pour afficher le **Gestionnaire de références**. Ce que vous voyez dans le Gestionnaire de références diffère selon le type de votre projet.  
  
 Dans un projet C\+\+ natif \(ATL\), le concept de *références* s’applique uniquement aux autres projets de la solution, notamment les projets partagés. Ainsi, vous ne voyez que cela dans le **Gestionnaire de références** :  
  
 ![Gestionnaire de références Visual C&#43;&#43; &#40;projets ATL&#41;](../Image/Visual%20C++%20Reference%20Manager%20\(ATL%20Projects\).png "Visual C\+\+ Reference Manager \(ATL Projects\)")  
  
 Dans un projet C\+\+\/CLI ou un projet de plateforme Windows universelle, le concept de références s’applique à plusieurs genres de fichiers binaires, en plus des autres projets de la solution.  Ceux\-ci sont tous exposés dans le **Gestionnaire de références** :  
  
 ![Gestionnaire de références Visual C&#43;&#43; pour les projets C&#43;&#43;&#47;CLI](../Image/Visual%20C++%20Reference%20Manager%20for%20C++/CLI%20projects.png "Visual C\+\+ Reference Manager for C\+\+\/CLI projects")  
  
## Propriétés de référence  
 Chaque genre de référence possède des propriétés. Pour afficher les propriétés, sélectionnez la référence dans l’Explorateur de solutions et appuyez sur **Alt\+Entrée**, ou cliquez avec le bouton droit et choisissez **Propriétés**. Certaines propriétés sont en lecture seule, et d’autres peuvent être modifiées. Toutefois, en règle générale, vous n’avez pas à modifier ces propriétés manuellement.  
  
### Propriétés de référence ActiveX  
 Les propriétés de référence ActiveX sont disponibles uniquement pour les références aux composants COM. Ces propriétés sont affichées uniquement quand un composant COM est sélectionné dans le volet **Références**. Les propriétés ne peuvent pas être modifiées.  
  
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
  
### Propriétés de la référence à l'assembly  
 Les propriétés de référence d'assembly sont disponibles uniquement pour les références aux assemblys [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] dans les projets C\+\+\/CLI. Ces propriétés sont affichées uniquement quand un assembly [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] est sélectionné dans le volet **Références**. Les propriétés ne peuvent pas être modifiées.  
  
 **Chemin d’accès relatif**  
 Affiche le chemin d'accès relatif du répertoire de projet à l'assembly référencé.  
  
### Propriétés de build  
 Les propriétés suivantes sont disponibles sur divers genres de références. Elles vous permettent de spécifier le mode de génération avec des références.  
  
 **Copie locale**  
 Spécifie si l'assembly référencé doit être copié automatiquement vers l'emplacement cible pendant une génération.  
  
 **Copier les assemblys satellites locaux**  
 Spécifie si les assemblys satellites de l'assembly référencé doivent être copiés automatiquement vers l'emplacement cible pendant une génération. Utilisé uniquement si **Copie locale** a la valeur `true`.  
  
 **Sortie de l’assembly de référence**  
 Spécifie que cet assembly est utilisé dans le processus de génération. Si la valeur est `true`, l'assembly est utilisé sur la ligne de commande du compilateur durant la génération.  
  
### Propriétés de référence entre projets  
 Les propriétés suivantes définissent une *référence entre projets*, depuis le projet sélectionné dans le volet **Références** vers un autre projet dans la même solution. Pour plus d'informations, consultez [Gestion des références dans un projet](../Topic/Managing%20references%20in%20a%20project.md).  
  
 **Lier les dépendances de la bibliothèque**  
 Quand cette propriété a la valeur **True**, le système de projet lie au projet dépendant les fichiers .lib produits par le projet indépendant. En général, vous devez spécifier **True**.  
  
 **Identificateur de projet**  
 Identifie de façon unique le projet indépendant. La valeur de propriété est un GUID système interne qui ne peut pas être modifié.  
  
 **Utiliser les entrées de dépendance de la bibliothèque**  
 Quand cette propriété a la valeur **False**, le système de projet ne lie pas au projet dépendant les fichiers .obj de la bibliothèque produite par le projet indépendant. Ainsi, cette valeur désactive la liaison incrémentielle. En général, vous spécifiez **False**, car la génération de l'application peut prendre du temps, s'il existe de nombreux projets indépendants.  
  
### Propriétés de référence  
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
 Pour les assemblys [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)], affiche le chemin d'accès complet. Pour les composants COM, affiche le GUID.  
  
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
  
## Voir aussi  
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)   
 [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md)