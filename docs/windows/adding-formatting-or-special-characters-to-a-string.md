---
title: "Adding Formatting or Special Characters to a String | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "special characters, adding to strings"
  - "ASCII characters, adding to strings"
  - "strings [C++], formatting"
  - "strings [C++], special characters"
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Adding Formatting or Special Characters to a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Pour ajouter des caractères de mise en forme ou des caractères spéciaux à une chaîne  
  
1.  Ouvrez la table de chaînes en double\-cliquant sur son icône dans l'[Affichage des ressources](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Si votre projet ne contient pas encore de fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Sélectionnez la chaîne que vous souhaitez modifier.  
  
3.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), ajoutez n'importe quelle séquence d'échappement standard en dessous du texte figurant dans la zone **Caption**, et appuyez sur **ENTRÉE**.  
  
    |Pour obtenir|Tapez|  
    |------------------|-----------|  
    |une nouvelle ligne|\\n|  
    |Retour chariot|\\r|  
    |Onglet|\\t|  
    |barre oblique inverse \(\\\)|\\\\|  
    |un caractère ASCII|\\ddd \(notation octale\)|  
    |une alerte \(mode sonore\)|\\a|  
  
> [!NOTE]
>  L'Éditeur de chaînes ne prend pas en charge l'intégralité des caractères d'échappement ASCII.  Vous ne pouvez utiliser que ceux qui sont répertoriés ci\-dessus.  
  
 Pour obtenir des informations sur l'ajout de ressources aux projets managés \(ceux qui ciblent le Common Language Runtime\), consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Configuration requise**  
  
 Win32  
  
## Voir aussi  
 [String Editor](../mfc/string-editor.md)   
 [Chaînes](_win32_Strings)   
 [À propos des chaînes](_win32_About_Strings_cpp)