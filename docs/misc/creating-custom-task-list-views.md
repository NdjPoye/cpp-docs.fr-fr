---
title: "Cr&#233;ation de vues de liste des t&#226;ches personnalis&#233;e | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Liste des tâches, vues personnalisées"
ms.assetid: c25f8f5d-55a1-4b5e-b617-3d1140bcb98a
caps.latest.revision: 13
caps.handback.revision: 13
manager: "douge"
---
# Cr&#233;ation de vues de liste des t&#226;ches personnalis&#233;e
Vous pouvez afficher une liste de tâches personnalisé dans Visual Studio en créant une vue personnalisée de la liste des tâches.  
  
 Utilisez le Registre pour créer un affichage personnalisé et effectuer les caractéristiques suivantes :  
  
-   les colonnes  
  
-   L'ordre de tri des colonnes  
  
-   l'ordre de tri par défaut  
  
-   Catégories de tâche à afficher  
  
 Vous pouvez afficher une catégorie personnalisée ou spécifier CAT\_ALL pour plusieurs catégories.  Vous pouvez également créer des colonnes personnalisées de texte qui contiennent n'importe quel texte.  Toutefois, vous ne pouvez pas trier sur les colonnes personnalisées de texte.  
  
 Les tableaux suivants présentent le format de Registre pour les vues personnalisées de liste des tâches.  
  
 Dans chacune des tables, *VS la racine de registre* est égal à \\Software\\Microsoft\\VisualStudio HKEY\_LOCAL\_MACHINE \\ 8,0 \\.  Les tables fournissent des entrées et des informations supplémentaires de script pour chaque instruction de Registre.  
  
 \[*VS la racine de registre*\\TaskList\\Views \\*GUID*\]  
  
|Nom|Type|Plage|Description|  
|---------|----------|-----------|-----------------|  
|Nom|REG\_SZ|Texte|nom de chaîne de la vue ou du \#xxx.<br /><br /> Le nom peut être une chaîne normalisée comme « ma vue personnalisée » ou une chaîne de ressource dans un package \(\#xxx\).|  
|Package|REG\_SZ|Texte|choisissez \[\] représentation sous forme de chaîne GUID.  Cela est obligatoire si certaines chaînes sont des chaînes de ressources \(\#xxx\) ; sinon, il est ignoré.|  
  
 \[*VS la racine de registre*\\TaskList\\Views \\*GUID*\\Columns \\*numéro*\]  
  
> [!NOTE]
>  *numéro* est la commande de base 1 de colonnes dans la vue \(où 1 représente la colonne la plus à gauche\).  pour plus de colonnes, incrément *numéro*.  
  
|Nom|Type|Plage|Description|  
|---------|----------|-----------|-----------------|  
|Champ|REG\_DWORD||<xref:Microsoft.VisualStudio.Shell.Interop.VSTASKFIELD> qui est le champ de la colonne.|  
|Largeur|REG\_DWORD||Facultatif.  Largeur de la colonne en pixels.  si la colonne n'est pas importante, ce paramètre est ignoré.|  
|Index|REG\_DWORD||Facultatif.  si le champ est FLD\_CUSTOM, c'est l'index de colonne personnalisé.|  
|Nom|REG\_SZ|Texte|Si le champ est FLD\_CUSTOM, il s'agit du nom de la colonne personnalisée.<br /><br /> Le nom peut également être une chaîne de ressources au format de \#xxx.|  
|Filter|REG\_SZ ou REG\_DWORD||Un DWORD qui a un élément VSTASKCATEGORY ou une CHAÎNE qui représente le GUID d'une catégorie personnalisée.|  
  
 \[*VS la racine de registre*\\TaskList\\Views \\*GUID*\\Sort \\*numéro*\]  
  
> [!NOTE]
>  *numéro* identifie la clé de tri.  Par exemple, pour la clé de tri principal, est égal à 1. de *numéro* .  Pour la clé de tri secondaire, *numéro* égal à 2, et ainsi de suite.  
  
|Nom|Type|Plage|Description|  
|---------|----------|-----------|-----------------|  
|Champ|REG\_DWORD||<xref:Microsoft.VisualStudio.Shell.Interop.VSTASKFIELD> qui est le champ de la colonne.|  
|Index|REG\_DWORD||Facultatif.  si le champ est FLD\_CUSTOM, c'est l'index de colonne personnalisé.|  
  
 Pour implémenter une colonne personnalisée, vous devez implémenter l'interface d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2> sur vos tâches et vous devez implémenter les méthodes suivantes sur cette interface :  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2.get_CustomColumnText%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2.put_CustomColumnText%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2.IsCustomColumnReadOnly%2A>  
  
 Si nécessaire, la liste des tâches interroge votre implémentation d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2> avec un numéro de colonne personnalisé d'une vue spécifique, représentée par *un certain GUID*.  Si votre tâche contient les informations appropriées sur cette colonne dans cette vue, vous indiquez les informations à cette colonne, et les spécifiez si ce texte est en lecture seule.  
  
## Voir aussi  
 [Procédure : création de catégories personnalisées de Listes des tâches](../misc/how-to-create-custom-categories-of-task-lists.md)