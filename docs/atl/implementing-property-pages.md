---
title: "Implementing Property Pages | Microsoft Docs"
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
  - "IPropertyPage class"
  - "IPropertyPage2 class"
  - "pages de propriétés, implémenter"
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing Property Pages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les pages de propriétés sont des objets COM qui implémentent `IPropertyPage` ou l'interface d' **IPropertyPage2** .  ATL fournit la prise en charge d'implémenter des pages de propriétés via [Assistant Page de propriétés ATL](../atl/reference/atl-property-page-wizard.md) dans [ajoutez la boîte de dialogue de classe](../ide/add-class-dialog-box.md).  
  
 Pour créer une page de propriétés à l'aide de ATL :  
  
-   Créez ou ouvrez un projet serveur de \(DLL\) de bibliothèque de liens dynamiques ATL.  
  
-   Ouvrez [ajoutez la boîte de dialogue de classe](../ide/add-class-dialog-box.md) et sélectionnez **ATL Property Page**.  
  
-   Assurez \-vous que votre page de propriétés est thread cloisonné \(puisqu'il possède une interface utilisateur\).  
  
-   Définissez le titre, la description \(chaîne de documents\), et le fichier d'aide à associer à votre page.  
  
-   Ajoutez des contrôles à la ressource de boîte de dialogue générée pour servir d'interface utilisateur de votre page de propriétés.  
  
-   Répondez aux modifications de l'interface utilisateur de votre page pour effectuer la validation, pour mettre à jour le site de page, ou mettre à jour les objets associés à votre page.  En particulier, appelez [IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md) lorsque l'utilisateur effectue des modifications à la page de propriétés.  
  
-   Substituez éventuellement les méthodes d' `IPropertyPageImpl` à l'aide de les instructions ci\-dessous.  
  
    |Méthode de IPropertyPageImpl|Substitution lorsque vous souhaitez…|Remarques|  
    |----------------------------------|------------------------------------------|---------------|  
    |[SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)|Exécutez les contrôles de base de validité sur le nombre d'objets passés à votre page et les interfaces qu'ils prennent en charge.|Exécutez votre propre code avant d'appeler l'implémentation de la classe de base.  Si les objets sont définis ne sont pas conformes à vos attentes, vous devez l'échec de l'appel dès que possible.|  
    |[Exécutez](../Topic/IPropertyPageImpl::Activate.md)|Initialisez l'interface utilisateur de votre page \(par exemple, définissez les contrôles de boîte de dialogue avec des valeurs de propriété actuelles des objets, créez les contrôles dynamiquement, ou effectuer d'autres initialisations\).|Appelez l'implémentation de la classe de base avant votre code afin que la classe de base a la possibilité de créer la fenêtre de dialogue et tous les contrôles avant d'essayer de les mettre à jour.|  
    |[Appliquer](../Topic/IPropertyPageImpl::Apply.md)|Validez les paramètres de propriété et mettre à jour les objets.|Il n'est pas nécessaire d'appeler l'implémentation de la classe de base puisqu'il ne fait rien en dehors de la trace l'appel.|  
    |[Mettez off](../Topic/IPropertyPageImpl::Deactivate.md)|Nettoyez les éléments liés aux fenêtres.|L'implémentation de la classe de base perd la boîte de dialogue qui représente la page de propriétés.  Si vous devez nettoyer avant la boîte de dialogue soit perdue, vous devez ajouter votre code avant d'appeler la classe de base.|  
  
 Pour obtenir un exemple d'implémentation de page de propriétés, consultez [exemple : implémenter une page de propriétés](../atl/example-implementing-a-property-page.md).  
  
> [!NOTE]
>  Si vous souhaitez héberger des contrôles ActiveX dans votre page de propriétés, vous devez modifier la dérivation de la classe générée par l'Assistant.  Remplacez **CDialogImpl\<CYourClass\>** par **CAxDialogImpl\<CYourClass\>** dans la liste de classes de base.  
  
## Voir aussi  
 [Pages de propriétés](../atl/atl-com-property-pages.md)   
 [Exemple ATLPages](../top/visual-cpp-samples.md)