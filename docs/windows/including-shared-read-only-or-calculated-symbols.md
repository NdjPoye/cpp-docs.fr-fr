---
title: "Including Shared (Read-Only) or Calculated Symbols | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.shared.calculated"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, read-only"
  - "symbols, shared"
  - "symbols, calculated"
  - "read-only symbols"
  - "symbol directives"
  - "calculated symbols"
  - "shared symbols"
ms.assetid: 32b77faf-a066-4371-a072-9a5b84c0766d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Including Shared (Read-Only) or Calculated Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La première fois que l'environnement de développement lit un fichier de ressources créé par une autre application, il marque tous les fichiers d'en\-tête inclus en lecture seule.  Vous pouvez utiliser ensuite la [boîte de dialogue Include des ressources](../windows/resource-includes-dialog-box.md) pour ajouter d'autres fichiers d'en\-tête de symbole en lecture seule.  
  
 Si vous envisagez de partager des fichiers de symboles entre plusieurs projets, vous pouvez utiliser les définitions de symbole en lecture seule.  
  
 Vous pouvez également utiliser des fichiers de symboles inclus quand vous disposez de ressources avec des définitions de symbole qui utilisent des expressions au lieu d'entiers simples pour définir la valeur du symbole.  Exemple :  
  
```  
#define   IDC_CONTROL1 2100  
#define   IDC_CONTROL2 (IDC_CONTROL1+1)  
```  
  
 L'environnement interprète correctement ces symboles calculés tant que les conditions suivantes sont respectées :  
  
-   Les symboles calculés sont placés dans un fichier de symboles en lecture seule.  
  
-   Votre fichier de ressources contient des ressources auxquelles ces symboles calculés sont déjà assignés.  
  
-   Une expression numérique est attendue.  
  
> [!NOTE]
>  Si une chaîne ou une expression numérique est attendue, l'expression n'est pas évaluée.  
  
### Pour inclure des symboles partagés \(en lecture seule\) dans votre fichier de ressources  
  
1.  Dans [Affichage des ressources](../windows/resource-view-window.md), cliquez avec le bouton droit sur le fichier .rc, puis choisissez [Include des ressources](../windows/resource-includes-dialog-box.md) dans le menu contextuel.  
  
    > [!NOTE]
    >  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans la zone **Directives de symboles en lecture seule**, utilisez la directive de compilateur **\#include** pour spécifier le fichier dans lequel les symboles en lecture seule doivent être conservés.  
  
     N'appelez pas le fichier Resource.h, car il s'agit du nom de fichier utilisé normalement par le fichier d'en\-tête de symbole principal.  
  
    > [!NOTE]
    >  **Important** Ce que vous tapez dans la zone Directives de symboles en lecture seule est inclus dans le fichier de ressources tel que vous le tapez.  Vérifiez que ce que vous tapez ne contient aucune erreur d'orthographe ou de syntaxe.  
  
     Utilisez la zone **Directives de symboles en lecture seule** pour inclure les fichiers contenant uniquement des définitions de symbole.  N'incluez pas de définitions de ressource. Sinon, des définitions de ressource en double seront créées durant l'enregistrement du fichier.  
  
3.  Placez les symboles dans le fichier spécifié.  
  
     Les symboles contenus dans les fichiers inclus de cette façon sont évalués chaque fois que vous ouvrez votre fichier de ressources. Toutefois, ils ne sont pas remplacés sur le disque quand vous enregistrez votre fichier.  
  
4.  Cliquez sur **OK**.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Symbol Value Restrictions](../windows/symbol-value-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)