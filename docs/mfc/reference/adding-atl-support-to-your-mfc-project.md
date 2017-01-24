---
title: "Ajout de la prise en charge ATL &#224; votre projet MFC | Microsoft Docs"
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
  - "vc.codewiz.adding.atl.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, projets MFC"
  - "MFC, prise en charge ATL"
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout de la prise en charge ATL &#224; votre projet MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Si vous avez déjà créé une application basée sur MFC, vous pouvez aisément ajouter la prise en charge ATL \(Active Template Library\) en exécutant l'Assistant Projet Ajouter la prise en charge ATL aux MFC.  
  
> [!NOTE]
>  ATL et MFC ne sont généralement pas pris en charge dans les éditions Express de Visual Studio.  
  
> [!NOTE]
>  Cette prise en charge s'applique uniquement aux objets simples COM ajoutés à un fichier exécutable MFC ou à un projet DLL.  Vous pouvez ajouter d'autres objets COM \(notamment des contrôles ActiveX\) à des projets MFC, mais il se peut que les objets ne fonctionnent pas de la manière souhaitée.  
  
### Pour ajouter la prise en charge ATL à votre projet MFC  
  
1.  Dans l'Explorateur de solutions, cliquez avec le bouton droit sur le projet auquel vous souhaitez ajouter la prise en charge ATL.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
3.  Sélectionnez l'icône **Ajouter la prise en charge ATL aux MFC**.  
  
    > [!NOTE]
    >  Cette icône se trouve dans le dossier ATL du volet **Catégories**.  
  
4.  Lorsque vous y êtes invité, cliquez sur **Oui** pour ajouter la prise en charge ATL.  
  
 Pour plus d'informations sur la manière dont l'ajout de la prise en charge ATL modifie le code de votre projet MFC, consultez [Détails de la prise en charge ATL ajoutée par l'Assistant ATL](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)  
  
## Voir aussi  
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d'une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d'une variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d'une fonction virtuelle](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC, gestionnaire de messages](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Parcours de la structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)