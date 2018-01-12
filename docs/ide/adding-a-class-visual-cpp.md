---
title: "Ajout d’une classe (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.classes.adding
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d767bd0afa85bc417cd33ce305ffe0061104bf64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-class-visual-c"></a>Ajout d'une classe (Visual C++)
Pour ajouter une classe dans un projet Visual C++, dans **l’Explorateur de solutions**, cliquez sur le projet, cliquez sur **ajouter**, puis cliquez sur **classe**. Cette opération ouvre le [boîte de dialogue Ajouter la classe](../ide/add-class-dialog-box.md) boîte de dialogue.  
  
 Lorsque vous ajoutez une classe, vous devez spécifier un nom différent à partir de classes qui existent déjà dans MFC ou ATL. Si vous spécifiez un nom qui existe déjà dans des deux bibliothèques, Visual C++ affiche un message qui indique que le nom spécifié est réservé.  
  
 Si votre projet de convention d’affectation de noms vous demande d’utiliser un nom existant, puis vous pouvez simplement modifier le cas d’une ou plusieurs lettres du nom, car Visual C++ respecte la casse. Par exemple, bien que vous ne pouvez pas nommer une classe `CDocument`, vous pouvez la nommer `cdocument`.  
  
## <a name="what-kind-of-class-do-you-want-to-add"></a>Le type de classe que vous souhaitez ajouter  
 Dans le **ajouter une classe** boîte de dialogue, lorsque vous développez le **Visual C++** nœud dans le volet gauche, plusieurs groupes de modèles installés sont affichés. Les groupes sont **CLR**, **ATL**, **MFC**, et **C++**. Lorsque vous sélectionnez un groupe, une liste des modèles disponibles dans ce groupe s’affiche dans le volet central. Chaque modèle contient les fichiers et le code source qui sont requises pour une classe.  
  
 Pour générer une nouvelle classe, sélectionnez un modèle dans le volet central, tapez un nom pour la classe dans le **nom** , puis cliquez sur **ajouter**. Cette opération ouvre le **Assistant Ajouter une classe** afin que vous pouvez spécifier des options pour la classe.  
  
-   Pour plus d’informations sur la création de classes de MFC, consultez [classe MFC](../mfc/reference/adding-an-mfc-class.md).  
  
-   Pour plus d’informations sur la création de classes ATL, consultez [objet Simple ATL](../atl/reference/adding-an-atl-simple-object.md).  
  
> [!NOTE]
>  Le modèle **ajouter la prise en charge ATL aux MFC** ne crée pas une classe, mais il configure le projet pour utiliser ATL. Pour plus d’informations, consultez [prise en charge ATL dans un projet MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
 Pour rendre une classe C++ qui n’utilise pas MFC, ATL ou CLR, utilisez le **classe C++** modèle dans le **C++** groupe de modèles installés. Pour plus d’informations, consultez [Ajout d’une classe C++ générique](../ide/adding-a-generic-cpp-class.md).  
  
 Deux types de classes C++ basées sur un formulaire sont disponibles. La première condition [CFormView, classe](../mfc/reference/cformview-class.md) crée une classe MFC. Le deuxième crée une classe CLR Windows Forms.  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’une Application MFC basée sur des formulaires](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [Ajouter la boîte de dialogue de classe](../ide/add-class-dialog-box.md)   
 [Création de projets du Bureau à l’aide des Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)