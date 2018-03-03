---
title: "Attributs IDL, Assistant Ajout de méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.method.idlattrib
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- IDL attributes, Add Method Wizard
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9792f8b7758ff5a1e5742b6643d9f73931bce6f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="idl-attributes-add-method-wizard"></a>Attributs IDL, Assistant Ajout de méthode
Utilisez cette page de l’Assistant Ajout de méthode pour spécifier les paramètres interface definition language (IDL) pour la méthode.  
  
 **ID**  
 Définit l’ID numérique qui identifie la méthode. Consultez [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) dans les *référence MIDL*.  
  
 Cette case n’est pas disponible pour les interfaces personnalisées et n’est pas disponible pour les dispinterfaces MFC.  
  
 **call_as**  
 Spécifie le nom d’une méthode distante à laquelle cette méthode locale peut être mappée. Consultez [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) dans les *référence MIDL*.  
  
 Non disponible pour les dispinterfaces MFC.  
  
 **helpcontext**  
 Spécifie un ID de contexte qui permet à l’utilisateur afficher des informations sur cette méthode dans le fichier d’aide. Consultez [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) dans les *référence MIDL*.  
  
 Non disponible pour les dispinterfaces MFC.  
  
 **helpstring**  
 Spécifie une chaîne de caractères qui est utilisée pour décrire l’élément auquel elle s’applique. Par défaut, il est défini « méthode *nom de la méthode*. » Consultez [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) dans les *référence MIDL*.  
  
 Non disponible pour les dispinterfaces MFC.  
  
 **Attributs supplémentaires**  
 Non disponible pour les dispinterfaces MFC.  
  
|Attribut|Description|  
|---------------|-----------------|  
|**hidden**|Indique que la méthode existe, mais ne doit pas être affichée dans un navigateur orienté utilisateur. Consultez [masqué](http://msdn.microsoft.com/library/windows/desktop/aa366861) dans les *référence MIDL*.|  
|**source**|Indique qu’un membre de la méthode est une source d’événements. Consultez [source](http://msdn.microsoft.com/library/windows/desktop/aa367166) dans les *référence MIDL*.|  
|`local`|Spécifie au compilateur MIDL que la méthode n’est pas à distance. Consultez [local](http://msdn.microsoft.com/library/windows/desktop/aa367071) dans les *référence MIDL*.|  
|**restricted**|Spécifie que la méthode ne peut pas être appelée arbitrairement. Consultez [restreint](http://msdn.microsoft.com/library/windows/desktop/aa367157) dans les *référence MIDL*.|  
|**vararg**|Spécifie que la méthode accepte un nombre variable d’arguments. Pour ce faire, le dernier argument doit être un tableau sécurisé de **VARIANT** type qui contient tous les arguments restants. Consultez [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) dans les *référence MIDL*.|  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une méthode](../ide/adding-a-method-visual-cpp.md)   
 [Assistant Ajout de méthode](../ide/add-method-wizard.md)