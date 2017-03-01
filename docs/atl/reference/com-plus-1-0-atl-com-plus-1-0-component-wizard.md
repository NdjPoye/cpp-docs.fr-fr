---
title: COM + 1.0, Assistant composant ATL COM + 1.0 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.options
dev_langs:
- C++
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 36295e5ce296ea6ba982c4ce8cf729bf45860883
ms.lasthandoff: 02/24/2017

---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0, Assistant Composant COM+ 1.0 ATL
Utilisez cette page de l’Assistant composant ATL COM + 1.0 pour spécifier le type d’interface et les interfaces supplémentaires à prendre en charge.  
  
 Pour plus d’informations sur les projets ATL et les classes ATL COM, consultez [composants de bureau ATL COM](../../atl/atl-com-desktop-components.md).  
  
 **Interface**  
 Indique le type d’interface que l’objet prend en charge. Par défaut, l’objet prend en charge une interface double.  
  
|Option|Description|  
|------------|-----------------|  
|**Double**|Spécifie que l’objet prend en charge une interface double (sa table vtable a des fonctions d’interface personnalisées et liaison tardive `IDispatch` méthodes). Permet à des clients COM et les contrôleurs Automation à accéder à l’objet.|  
|**Personnalisé**|Spécifie que l’objet prend en charge une interface personnalisée (sa table vtable a des fonctions d’interface personnalisées). Une interface personnalisée peut être plus rapide qu’une interface double, en particulier les limites du processus.<br /><br /> -   **Compatible Automation** ajoute la prise en charge de l’automation à l’interface personnalisée. Pour les projets avec attributs, définit les **oleautomation** attribut dans la coclasse.|  
  
 **Pouvant**  
 Indique que les clients peuvent appeler ce composant de manière asynchrone à l’aide de files d’attente. Ajoute la macro personnalisée avec composants (TLBATTR_QUEUEABLE, 0) au fichier .h (projets attribués) ou au fichier .idl (projets sans attributs).  
  
 **Prise en charge**  
 Indique la prise en charge supplémentaire pour le contrôle de la gestion et l’objet d’erreur.  
  
|Option|Description|  
|------------|-----------------|  
|**ISupportErrorInfo**|Crée la prise en charge de la [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) interface afin que l’objet puisse retourner des informations d’erreur au client.|  
|**IObjectControl**|Fournit l’accès de l’objet à trois [IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474) méthodes : [activer](http://msdn.microsoft.com/library/windows/desktop/ms681303), [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322), et [Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms687094).|  
|**IObjectConstruct**|Crée la prise en charge de la [IObjectConstruct](http://msdn.microsoft.com/library/windows/desktop/ms680583) interface pour gérer le passage des paramètres à partir d’autres méthodes ou objets.|  
  
 **Transaction**  
 Indique que l’objet prend en charge les transactions. Inclut le fichier mtxattr.h dans le fichier .idl (projets sans attributs).  
  
|Option|Description|  
|------------|-----------------|  
|**Prise en charge**|Spécifie que l’objet n’est jamais la racine d’un flux de transactions en ajoutant la custom(TLBATTR_TRANS_SUPPORTED,0) de macro attribut composant au fichier .h (projets attribués) ou au fichier .idl (projets sans attributs).|  
|**Obligatoire**|Spécifie que l’objet peut peut-être pas la racine d’un flux de transactions en ajoutant la custom(TLBATTR_TRANS_REQUIRED,0) de macro attribut composant au fichier .h (projets attribués) ou au fichier .idl (projets sans attributs).|  
|**Non pris en charge**|Spécifie que l’objet exclut les transactions. Ajoute le custom(TLBATTR_TRANS_NOTSUPP,0) de macro attribut composant au fichier .h (projets attribués) ou au fichier .idl (projets sans attributs).|  
|**Requiert une nouvelle**|Spécifie que l’objet est toujours la racine d’un flux de transactions en ajoutant la custom(TLBATTR_TRANS_REQNEW,0) de macro attribut composant au fichier .h (projets attribués) ou au fichier .idl (projets sans attributs).|  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant 1.0 composant ATL COM +](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [Composant ATL COM + 1.0](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)


