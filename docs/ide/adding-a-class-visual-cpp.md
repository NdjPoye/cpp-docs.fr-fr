---
title: "Ajout d&#39;une classe (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.classes.adding"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, ajouter des classes"
  - "classes (C++), ajouter"
  - "classes (C++), créer"
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
caps.latest.revision: 24
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;une classe (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour ajouter une classe dans un projet Visual C\+\+, dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le projet, cliquez sur **Ajouter**, puis sur **Classe**.  Cela permet d'ouvrir la boîte de dialogue [Boîte de dialogue Ajouter une classe](../ide/add-class-dialog-box.md).  
  
 Lorsque vous ajoutez une classe, vous devez spécifier un nom différent de celui des classes qui existent déjà dans MFC ou ATL.  Si vous entrez un nom qui existe déjà dans l'une des deux bibliothèques, Visual C\+\+ affiche un message qui indique que le nom spécifié est réservé.  
  
 Si la convention de dénomination de votre projet exige que vous utilisiez un nom existant, il vous suffit de modifier la casse d'une ou de plusieurs lettres du nom, car Visual C\+\+ respecte la casse.  Par exemple, bien que vous ne puissiez pas nommer une classe `CDocument`, vous pouvez la nommer `cdocument`.  
  
## Quel genre de classe voulez\-vous ajouter ?  
 Dans la boîte de dialogue **Ajouter une classe**, lorsque vous développez le nœud **Visual C\+\+** dans le volet gauche, plusieurs groupes de classes installées s'affichent.  Il s'agit notamment des groupes suivants : **CLR**, **ATL**, **MFC** et **C\+\+**.  Lorsque vous sélectionnez un groupe, la liste des modèles disponibles dans ce groupe s'affiche dans le volet central.  Chaque modèle contient les fichiers et le code source requis pour une classe.  
  
 Pour générer une nouvelle classe, sélectionnez un modèle dans le volet central, tapez le nom de la classe dans la zone **Nom**, puis cliquez sur **Ajouter**.  Cela entraîne l'affichage de l'**Assistant Ajouter une classe**, qui vous permet de spécifier les options relatives à la classe.  
  
-   Pour plus d'informations sur la création de classes MFC, consultez [MFC, classe](../mfc/reference/adding-an-mfc-class.md).  
  
-   Pour plus d'informations sur la création de classes ATL, consultez [ATL Simple Object](../atl/reference/adding-an-atl-simple-object.md).  
  
> [!NOTE]
>  Le modèle **Ajouter la prise en charge ATL aux MFC** ne crée pas de classe, mais il configure le projet pour une utilisation d'ATL.  Pour plus d'informations, consultez [Prise en charge ATL dans un projet MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
 Pour créer une classe C\+\+ qui n'utilise pas MFC, ATL ou CLR, servez\-vous du modèle **Classe C\+\+** situé dans le groupe **C\+\+** des classes installées.  Pour plus d'informations, consultez [Ajout d'une classe C\+\+ générique](../ide/adding-a-generic-cpp-class.md).  
  
 Deux genres de classes C\+\+ basées sur formulaires sont disponibles.  Le premier, [CFormView Class](../mfc/reference/cformview-class.md) crée une classe MFC.  Le deuxième crée une classe CLR Windows Forms.  
  
## Voir aussi  
 [Création d'une application MFC basée sur les formulaires](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [Boîte de dialogue Ajouter une classe](../ide/add-class-dialog-box.md)   
 [Création de projets de bureau à l'aide des Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)