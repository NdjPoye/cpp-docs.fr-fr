---
title: "D&#233;finition des propri&#233;t&#233;s du contr&#244;le au moment du design | Microsoft Docs"
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
  - "contrôles ActiveX (C++), propriétés"
ms.assetid: 963bf498-d371-4cfd-8bed-865427dcfad9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finition des propri&#233;t&#233;s du contr&#244;le au moment du design
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les propriétés des contrôles peuvent être définies au moment du design à l'aide de l'Éditeur de boîtes de dialogue.  Lorsque vous définissez une propriété, l'Éditeur de ressources initialise le contrôle avec la valeur spécifiée.  Vous avez toujours la possibilité de modifier la propriété par programme.  
  
 La propriété **DataSource**, qui figure dans tous les [contrôles liés aux données](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md), permet de spécifier le contrôle de [source de données](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md) avec lequel vous voulez établir la liaison.  
  
 Lorsque vous liez de simples contrôles ADO liés aux données à un contrôle de données ADO \(ADODC\), vous devez associer le contrôle à une colonne en affectant la propriété **DataField** à un champ valide dans le jeu de lignes.  Sinon, l'application compilée est évaluée dans la version Debug exécutée \(cette procédure dite d'assertion désigne simplement le fait de marquer le contrôle comme étant lié à une colonne nulle\).  
  
> [!NOTE]
>  L'onglet de propriétés **Général** permet de spécifier un identificateur de contrôle et d'autres propriétés nécessaires pour le fichier .rc. \(Le fichier .rc est compilé ultérieurement afin de générer un code de ressources de programme Windows.\)  
  
### Pour insérer une propriété sous l'onglet Tout  
  
1.  [Insérez un contrôle ActiveX](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md) dans une boîte de dialogue.  
  
2.  Cliquez avec le bouton droit dans l'Éditeur de boîtes de dialogue, puis cliquez sur **Propriétés**.  
  
3.  Cliquez sur l'onglet **Tout** pour afficher les propriétés du contrôle.  Entrez la valeur d'initialisation d'une propriété particulière.  
  
 Pour définir les propriétés d'un contrôle au moment de l'exécution, consultez [Modification du comportement d'un contrôle au moment de l'exécution](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md).  
  
## Voir aussi  
 [Utilisation des contrôles ActiveX](../../data/ado-rdo/using-activex-controls.md)