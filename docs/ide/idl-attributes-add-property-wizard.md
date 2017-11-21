---
title: "Attributs IDL, Assistant Ajout de propriété | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.prop.idlattributes
dev_langs: C++
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8dd58ebd25c3b70b10ae3530577d70058bef5b86
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="idl-attributes-add-property-wizard"></a>Attributs IDL, Assistant Ajout de propriété
Utilisez cette page de l’Assistant Ajout de propriété pour spécifier les paramètres interface definition language (IDL) pour la propriété.  
  
 **id**  
 Définit l’ID numérique qui identifie la propriété. Cette option n’est pas disponible pour les propriétés des interfaces personnalisées. Consultez [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) dans les *référence MIDL*.  
  
 **helpcontext**  
 Spécifie un ID de contexte qui permet à l’utilisateur afficher des informations sur cette propriété dans le fichier d’aide. Consultez [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) dans les *référence MIDL*.  
  
 **helpstring**  
 Spécifie une chaîne de caractères qui est utilisée pour décrire l’élément auquel elle s’applique. Par défaut, il est défini « propriété *nom de la propriété*. » Consultez [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) dans les *référence MIDL*.  
  
## <a name="other-options"></a>Autres options  
 Toutes les options sont disponibles pour tous les types de propriété.  
  
|Option|Description|  
|------------|-----------------|  
|**bindable**|Indique que la propriété prend en charge la liaison de données. Consultez [pouvant être liés](http://msdn.microsoft.com/library/windows/desktop/aa366738) dans les *référence MIDL*. Pour l’implémentation de la propriété stock, cette option a la valeur par défaut et n’est pas modifiable.|  
|**defaultbind**|Indique que la propriété unique, pouvant être liée meilleures représente l’objet. Consultez [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790) dans les *référence MIDL*.|  
|**displaybind**|Indique que cette propriété doit être affichée à l’utilisateur comme pouvant être liée. Consultez [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804) dans les *référence MIDL*.|  
|**immediatebind**|Indique que la base de données est immédiatement avertie de toutes les modifications apportées à cette propriété d’un objet lié aux données. Consultez [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045) dans les *référence MIDL*.|  
|**defaultcollelem**|Indique que la propriété est une fonction d’accesseur pour un élément de la collection par défaut. Consultez [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792) dans les *référence MIDL*.|  
|**nonbrowsable**|Un membre d’interface ou une dispinterface ne doit pas être affiché dans un navigateur de propriétés des balises. Consultez [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) dans les *référence MIDL*.|  
|**requestedit**|Indique que la propriété prend en charge la **OnRequestEdit** notification voir [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155) dans les *référence MIDL*. Pour l’implémentation de la propriété stock, cette option a la valeur par défaut et n’est pas modifiable.|  
|**source**|Indique qu’un membre de la propriété est une source d’événements. Consultez [source](http://msdn.microsoft.com/library/windows/desktop/aa367166) dans les *référence MIDL*.|  
|**hidden**|Indique que la propriété existe mais qu’il ne doit pas être affichée dans un navigateur orienté utilisateur. Consultez [masqué](http://msdn.microsoft.com/library/windows/desktop/aa366861) dans les *référence MIDL*.|  
|**restricted**|Spécifie que la propriété ne peut pas être appelée arbitrairement. Consultez [restreint](http://msdn.microsoft.com/library/windows/desktop/aa367157) dans les *référence MIDL*.|  
|`local`|Spécifie au compilateur MIDL que la propriété n’est pas distante. Consultez [local](http://msdn.microsoft.com/library/windows/desktop/aa367071) dans les *référence MIDL*.|  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une propriété](../ide/adding-a-property-visual-cpp.md)   
 [Noms, Assistant Ajout de propriété](../ide/names-add-property-wizard.md)   
 [Implémentation d’une Interface](../ide/implementing-an-interface-visual-cpp.md)   
 [Propriétés stock](../ide/stock-properties.md)