---
title: "Implementing a Dual Interface | Microsoft Docs"
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
  - "interfaces doubles, implémenter"
  - "classe IDispatchImpl, implementing dual interfaces"
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing a Dual Interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez implémenter une interface double à l'aide de la classe d' [IDispatchImpl](../atl/reference/idispatchimpl-class.md) , qui fournit une implémentation par défaut des méthodes d' `IDispatch` dans une interface double.  Pour plus d'informations, consultez [Implementing the IDispatch Interface](http://msdn.microsoft.com/fr-fr/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
 Pour utiliser cette classe :  
  
-   Définissez votre interface double dans une bibliothèque de types.  
  
-   Dérivez votre classe d'une spécialisation d' `IDispatchImpl` \(informations de exécution sur l'interface et la bibliothèque de types comme arguments template\).  
  
-   Ajoutez une entrée \(ou les entrées\) au mappage COM pour exposer l'interface double dans `QueryInterface`.  
  
-   Implémentez la partie vtable de l'interface dans votre classe.  
  
-   Vérifiez que la bibliothèque de types qui contient la définition d'interface est disponible à vos objets au moment de l'exécution.  
  
## Assistant Objet simple ATL  
 Si vous souhaitez créer une nouvelle interface et une classe pour l'implémenter, vous pouvez utiliser [ATL ajoute la boîte de dialogue de classe](../ide/add-class-dialog-box.md), puis [Assistant Objet simple ATL](../atl/reference/atl-simple-object-wizard.md).  
  
## Assistant Implémentation d'interface  
 Si vous avez une interface existante, vous pouvez utiliser [Assistant Implémentation d'interface](../atl/reference/adding-a-new-interface-in-an-atl-project.md) pour ajouter la classe de base nécessaire, les entrées de mappage COM, et les implémentations squelettiques de méthode à une classe existante.  
  
> [!NOTE]
>  Vous devrez peut\-être ajuster la classe de base générée afin que les numéros de version secondaire de la bibliothèque de types sont passés comme arguments template à votre classe de base d' `IDispatchImpl` .  Assistant Implémentation d'interface ne vérifie pas le numéro de version de la bibliothèque de types pour rechercher vous.  
  
## Implémenter IDispatch  
 Vous pouvez utiliser une classe de base d' `IDispatchImpl` pour fournir une implémentation d'une dispinterface simplement en spécifiant l'entrée appropriée dans le mappage COM \(à l'aide de la macro de [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) ou de [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md) \) tant que vous avez une bibliothèque de types décrivant une interface double correspondante.  Il est assez courante pour implémenter l'interface d' `IDispatch` de cette façon, par exemple.  Assistant Objet simple ATL et l'Assistant Implémentation d'interface elles supposent que vous avez l'intention d'implémenter `IDispatch` de cette façon, afin qu'ils ajouteront l'entrée appropriée au mappage.  
  
> [!NOTE]
>  ATL offre les classes d' [IDispEventImpl](../atl/reference/idispeventimpl-class.md) et d' [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) pour mieux isoler les dispinterfaces d'implémenter sans nécessiter une bibliothèque de types qui contient la définition d'une interface double compatible.  
  
## Voir aussi  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)