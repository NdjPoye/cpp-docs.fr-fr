---
title: "COM+&#160;1.0, Assistant Composant COM+&#160;1.0 ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.mts.options"
dev_langs: 
  - "C++"
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM+&#160;1.0, Assistant Composant COM+&#160;1.0 ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant Composant ATL COM\+ 1.0 pour spécifier le type d'interface et les interfaces supplémentaires à prendre en charge.  
  
 Pour plus d'informations sur les projets ATL et les classes ATL COM, consultez [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md).  
  
 **Interface**  
 Indique le type d'interface pris en charge par l'objet.  Par défaut, l'objet prend en charge une interface double.  
  
|Option|Description|  
|------------|-----------------|  
|**Double**|Spécifie que l'objet prend en charge une interface double \(sa table de fonctions virtuelles, vtable, possède des fonctions d'interface personnalisées, ainsi que des méthodes `IDispatch` de liaison tardive\).  Autorise à la fois les clients COM et les contrôleurs Automation à accéder à l'objet.|  
|**Personnalisé**|Spécifie que l'objet prend en charge une interface personnalisée \(sa table de fonctions virtuelles, vtable, possède des fonctions d'interface personnalisées\).  Une interface personnalisée peut être plus rapide qu'une interface double, particulièrement pour les opérations interprocessus.<br /><br /> -   **Automation compatible** ajoute la prise en charge d'automation à l'interface personnalisée.  Pour les projets avec attributs, définit l'attribut **oleautomation** dans la coclasse.|  
  
 **Possibilité de mise en file d'attente**  
 Indique que les clients peuvent appeler ce composant de manière asynchrone à l'aide de files d'attente de messages.  Ajoute la macro personnalisée avec attributs de composants \(TLBATTR\_QUEUEABLE, 0\) au fichier .h \(projets avec attributs\) ou au fichier .idl \(projets sans attributs\).  
  
 **Prise en charge**  
 Indique la prise en charge supplémentaire du traitement des erreurs et du contrôle des objets.  
  
|Option|Description|  
|------------|-----------------|  
|**ISupportErrorInfo**|Crée une prise en charge pour l'interface [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) afin que l'objet puisse retourner au client des informations sur les erreurs.|  
|**IObjectControl**|Permet à votre objet d'accéder aux trois méthodes [IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474) : [Activate](http://msdn.microsoft.com/library/windows/desktop/ms681303), [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322) et [Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms687094).|  
|**IObjectConstruct**|Permet à l'interface [IObjectConstruct](http://msdn.microsoft.com/library/windows/desktop/ms680583) de gérer le passage de paramètres provenant d'autres méthodes ou objets.|  
  
 **Transaction**  
 Indique que l'objet prend en charge les transactions.  Inclut le fichier mtxattr.h dans le fichier .idl \(projets sans attributs\).  
  
|Option|Description|  
|------------|-----------------|  
|**Pris en charge**|Spécifie que l'objet n'est jamais la racine d'un flux de transactions en ajoutant la personnalisation de la macro de l'attribut du composant \(TLBATTR\_TRANS\_SUPPORTED,0\) au fichier .h \(projets avec attributs\) ou au fichier .idl \(projets sans attributs\).|  
|**Obligatoire**|Spécifie que l'objet peut être éventuellement la racine d'un flux de transactions en ajoutant la personnalisation de la macro de l'attribut du composant \(TLBATTR\_TRANS\_REQUIRED,0\) au fichier .h \(projets avec attributs\) ou au fichier .idl \(projets sans attributs\).|  
|**Non pris en charge**|Spécifie que l'objet exclut les transactions.  Ajoute la personnalisation de la macro attribuée au composant \(TLBATTR\_TRANS\_NOTSUPP,0\) au fichier .h \(projets avec attributs\) ou au fichier .idl \(projets sans attributs\).|  
|**Requiert nouveau**|Spécifie que l'objet est toujours la racine d'un flux de transactions en ajoutant la personnalisation de la macro de l'attribut du composant \(TLBATTR\_TRANS\_REQNEW,0\) au fichier .h \(projets avec attributs\) ou au fichier .idl \(projets sans attributs\).|  
  
## Voir aussi  
 [Composant ATL COM\+ 1.0 \(Assistant\)](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM\+ 1.0 Component](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)