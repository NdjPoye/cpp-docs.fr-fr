---
title: "Fichiers cr&#233;&#233;s pour votre Assistant | Microsoft Docs"
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
  - "Assistants personnalisés, supprimer des fichiers"
  - "Assistants personnalisés, fichiers créés"
  - "fichiers (C++), créés par l'Assistant personnalisé"
  - "icônes, supprimer"
ms.assetid: 7f0e393c-395e-491b-add2-904cf8838e81
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers cr&#233;&#233;s pour votre Assistant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre Assistant utilise le nom spécifié dans la case **Nom** de la boîte de dialogue **Nouveau projet** pour dériver les noms de certains fichiers et classes.  
  
 L'[Assistant personnalisé](../ide/custom-wizard.md) ajoute des commentaires aux fichiers qu'il crée pour votre Assistant.  L'Assistant personnalisé crée aussi un fichier texte, ReadMe.txt, dans votre nouveau répertoire d'application.  Ce fichier détaille le contenu et l'utilisation des autres fichiers créés par l'Assistant personnalisé.  
  
 La table ci\-dessous décrit les fichiers créés par l'Assistant personnalisé.  Pour plus d'informations sur la façon dont les éléments clés interagissent pour créer un Assistant, consultez [Conception d'un Assistant](../ide/designing-a-wizard.md).  
  
|Fichier|Description|  
|-------------|-----------------|  
|[Project.vsz](../ide/dot-vsz-file-project-control.md)|Fichier texte similaire à l'ancien format .ini.  Il identifie le moteur d'Assistant et fournit des informations de contexte et des [paramètres personnalisés](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md) facultatifs.|  
|[Project.vsdir](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)|Fichier texte qui permet au shell Visual Studio de rechercher l'Assistant et de l'afficher dans la boîte de dialogue **Nouveau projet**.|  
|[Fichiers HTML \(facultatifs\)](../ide/html-files.md)|Un Assistant peut contenir une interface utilisateur \(UI\), qui est une interface HTML.  Un Assistant sans interface utilisateur ne contient pas de fichiers HTML.<br /><br /> Si un Assistant a une interface utilisateur, chaque écran de l'Assistant est appelé *page* et chaque page spécifie des fonctionnalités d'interface utilisateur.<br /><br /> Le fichier default.htm définit la première page de l'Assistant.  Utilisez la zone de liste **Nombre de pages** dans [Paramètres d'application, Assistant personnalisé](../ide/application-settings-custom-wizard.md) pour spécifier des pages supplémentaires.  Chaque page supplémentaire est définie par un fichier Page\_*numéro\-de\-page*.htm, où *numéro\-de\-page* est compris entre 2 et le nombre de pages que vous spécifiez.|  
|[Fichiers de script](../ide/jscript-file.md)|L'Assistant personnalisé crée un fichier JScript, default.js, pour chaque Assistant créé.  Ce fichier contient des fonctions JScript qui accèdent à l'Assistant, au code et aux modèles objets d'environnement Visual C\+\+ pour personnaliser un Assistant.  Vous pouvez personnaliser et ajouter des fonctions au fichier default.js de votre Assistant.<br /><br /> En outre, votre Assistant inclut le fichier [common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md), qui contient des fonctions JScript communément utilisées, et est partagé par tous les Assistants, notamment les Assistants utilisés par Visual C\+\+ pour créer d'autres types de projets.  Pour plus d'informations, consultez [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md).|  
|[Modèles](../ide/template-files.md)|Les modèles d'un Assistant sont un ensemble de fichiers texte qui contiennent des directives, analysées et insérées dans la table de symboles en fonction des sélections de l'utilisateur de l'Assistant.  Les fichiers texte modèles sont restitués d'après les entrées utilisateur et sont ajoutés au projet créé par l'Assistant.  Les informations appropriées sont obtenues par accès direct à la table de symboles des contrôles de l'Assistant.|  
|[Templates.inf](../ide/templates-inf-file.md)|Fichier texte qui contient la liste de tous les modèles associés au projet.|  
|Default.vcxproj|Fichier .xml qui contient des informations à propos du type de projet.|  
|Sample.txt|Fichier modèle présentant l'utilisation de vos directives d'Assistant.|  
|ReadMe.txt|Fichier modèle qui contient un résumé de chacun des fichiers créés par l'Assistant personnalisé.|  
|Images \(facultatif\)|Vous pouvez fournir des images, telles que des icônes, fichiers GIF, BMP et autres formats d'image pris en charge par HTML, pour améliorer l'interface utilisateur de votre Assistant.  Un Assistant qui n'a pas d'interface utilisateur ne nécessite pas d'images.|  
|Styles.css \(facultatif\)|Fichier définissant les styles de l'interface utilisateur.  Si votre Assistant n'a pas d'interface utilisateur, l'Assistant personnalisé ne crée pas de fichier .css.|  
  
 Si vous supprimez les fichiers et les répertoires de votre Assistant, vous devez également supprimer les fichiers suivants du répertoire \\vc7\\vcprojects\\.  Tant que vous n'aurez pas supprimé ces fichiers, les icônes de votre Assistant apparaîtront dans la boîte de dialogue **Nouveau projet**.  
  
-   *nomprojet*.vsz  
  
-   *nomprojet*.ico  
  
-   *nomprojet*.vsdir  
  
## Voir aussi  
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)