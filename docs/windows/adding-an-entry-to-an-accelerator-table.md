---
title: "Ajout d&#39;une entr&#233;e dans une table d&#39;acc&#233;l&#233;rateurs | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "tables d’accélérateurs (C++), ajouter des entrées"
  - "Nouvel accélérateur (commande)"
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;une entr&#233;e dans une table d&#39;acc&#233;l&#233;rateurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### <a name="to-add-an-entry-to-an-accelerator-table"></a>Pour ajouter une entrée à une table d'accélérateurs  
  
1.  Ouvrez la table d’accélérateurs en double-cliquant sur son icône dans [affichage des ressources](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Avec le bouton droit dans la table d’accélérateurs et choisissez **Nouvel accélérateur** dans le menu contextuel, ou cliquez sur la ligne vide en bas de la table.  
  
3.  Sélectionnez un [ID](Id%20Property.xml) dans la liste déroulante dans l’ID de zone ou tapez un nouvel ID dans la **ID** boîte.  
  
4.  Type le [clé](../windows/accelerator-key-property.md) vous souhaitez utiliser comme accélérateur ou avec le bouton droit et choisissez **suivante** dans le menu contextuel pour définir une combinaison de touches (la **enfoncée suivante** commande est également disponible à partir de la **Modifier** menu).  
  
5.  Modifier la [modificateur](../windows/accelerator-modifier-property.md) et [Type](../windows/accelerator-type-property.md), si nécessaire.  
  
6.  Appuyez sur **ENTRÉE**.  
  
    > [!NOTE]
    >  Assurez-vous que tous les accélérateurs définis sont uniques. Plusieurs combinaisons de touches peuvent être assignées au même ID sans problème. Par exemple, Ctrl + P et F8 peuvent être assignées à ID_PRINT. Toutefois, l'assignation d'une combinaison de touches à plusieurs ID ne fonctionne pas correctement. C'est le cas, par exemple, si la combinaison Ctrl + Z est assignée à ID_SPELL_CHECK et ID_THESAURUS.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, consultez [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Requirements**  
  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Modification des Tables d’accélérateurs](../windows/editing-accelerator-tables.md)   
 [Éditeur d’accélérateurs](../mfc/accelerator-editor.md)