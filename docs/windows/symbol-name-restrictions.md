---
title: "Symbol Name Restrictions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.restrictions.name"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbol names"
  - "symbols, names"
  - "restrictions, symbol names"
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Symbol Name Restrictions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les restrictions relatives aux noms de symboles sont les suivantes :  
  
-   Tous les [symboles](../mfc/symbols-resource-identifiers.md) doivent être uniques dans l'étendue de l'application.  Cela empêche les conflits de définitions de symbole dans les fichiers d'en\-tête.  
  
-   Les caractères valides pour un nom de symbole incluent A\-Z, a\-z, 0\-9 et les traits de soulignement \(\_\).  
  
-   Les noms de symboles ne peuvent pas commencer par un chiffre. Par ailleurs, ils sont limités à 247 caractères.  
  
-   Les noms de symboles ne peuvent pas contenir d'espaces.  
  
-   Les noms de symboles ne respectent pas la casse. Toutefois, la casse de la première définition de symbole est conservée.  Le fichier d'en\-tête qui définit les symboles est utilisé par le compilateur\/l'éditeur de ressources, ainsi que par le ou les programmes C\+\+ pour faire référence aux ressources définies dans un fichier de ressources.  Quand deux noms de symboles diffèrent uniquement par la casse, le programme C\+\+ identifie deux symboles distincts alors que le compilateur\/l'éditeur de ressources identifie les deux noms comme faisant référence à un symbole unique.  
  
    > [!NOTE]
    >  Si vous ne suivez pas le modèle de nom de symbole standard \(ID\*\_\[keyword\]\) décrit ci\-dessous, et si votre nom de symbole est identique à un mot clé connu du compilateur de script de ressources, la génération du fichier de script de ressources entraînera des erreurs aléatoires difficiles à diagnostiquer.  Pour éviter cela, respectez le modèle d'affectation de noms standard.  
  
 Les noms de symboles comportent des préfixes descriptifs qui indiquent le genre de ressource ou d'objet qu'ils représentent.  Ces préfixes descriptifs commencent par la combinaison de texte ID.  La bibliothèque MFC \(Microsoft Foundation Class\) utilise les conventions d'affectation de noms de symboles illustrées dans le tableau suivant.  
  
|Catégorie|Préfixe|Utilisation|  
|---------------|-------------|-----------------|  
|Ressources|IDR\_ IDD\_ IDC\_ IDI\_ IDB\_|Accélérateur ou menu \(et ressources associées ou personnalisées\), boîte de dialogue, curseur, icône, image bitmap|  
|Éléments de menu|ID\_|Menu Item|  
|Commandes|ID\_|Commande|  
|Contrôles et fenêtres enfants|IDC\_|Contrôle|  
|Chaînes|IDS\_|Chaîne dans la table de chaînes|  
|MFC|AFX\_|Réservé aux symboles MFC prédéfinis|  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d'informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, voir [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Changing a Symbol or Symbol Name \(ID\)](../windows/changing-a-symbol-or-symbol-name-id.md)   
 [Symbol Value Restrictions](../windows/symbol-value-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)