---
title: "Noms, Assistant Ajout de propriété | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.prop.overview
dev_langs:
- C++
ms.assetid: 0453b7ea-89cb-41a1-80a2-d45f61589c0a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c1728dfda3ec29e8df2b7f5480e9bffb161da7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="names-add-property-wizard"></a>Noms, Assistant Ajout de propriété
Utilisez cet Assistant pour ajouter une propriété à une interface.  
  
 **Type de propriété**  
 Définit le type de propriété que vous ajoutez. Pour les dispinterfaces MFC, fournir votre propre type, ou sélectionnez dans la liste prédéfinie. Si vous fournissez une implémentation stock d’une propriété, **type de propriété** est définie sur le type de stock et n’est pas disponible pour modification.  
  
 **Nom de propriété**  
 Définit le nom de la propriété. Pour les dispinterfaces MFC associées aux contrôles ActiveX, vous pouvez fournir votre propre nom, ou vous pouvez sélectionner un nom de propriété stock dans la liste prédéfinie. Si vous fournissez votre propre nom de propriété, le **Stock** type d’implémentation n’est pas disponible. Consultez [Propriétés Stock](../ide/stock-properties.md) pour obtenir une description des propriétés dans la liste.  
  
|Type d'interface|Description|  
|--------------------|-----------------|  
|Interface double ATL, interface personnalisée et interface locale personnalisée|Fournissez un nom de propriété.|  
|Dispinterface MFC, dispinterface du contrôle ActiveX MFC|Fournissez un nom de propriété ou sélectionnez une propriété stock dans la liste. Si vous sélectionnez une propriété dans la liste, la valeur appropriée s’affiche dans le **type de propriété** boîte. Vous pouvez modifier ce type, en fonction de votre sélection sous **type d’implémentation**.|  
  
 **Type de retour**  
 Interfaces ATL uniquement. Définit le type de retour pour la propriété. Pour les interfaces doubles, `HRESULT` est toujours le type de retour, et cette zone n’est pas disponible. Pour les interfaces personnalisées, vous pouvez sélectionner un type de retour dans la liste. `HRESULT`est toujours recommandée, car il offre un moyen standard de retourner des erreurs.  
  
 **Nom de variable**  
 Dispinterfaces MFC uniquement. Disponible uniquement si vous spécifiez **variable membre** sous **type d’implémentation**. Définit le nom de la variable membre à laquelle la propriété est associée. Par défaut, le nom de variable est défini sur m_*PropertyName*. Vous pouvez modifier ce nom.  
  
 **Fonction de notification**  
 Dispinterfaces MFC uniquement. Disponible uniquement si vous spécifiez **variable membre** sous **type d’implémentation**. Définit le nom de la fonction de notification appelée si les modifications de propriété. Par défaut, le nom de la fonction de notification est activé*PropertyName*a été modifié. Vous pouvez modifier ce nom.  
  
 **Get, fonction**  
 Pour les dispinterfaces MFC. Disponible uniquement si vous spécifiez **méthodes Get/Set** sous **type d’implémentation**. Définit le nom de la fonction pour obtenir la propriété. Par défaut, le nom de la fonction Get est défini à Get*PropertyName*. Vous pouvez modifier ce nom. Si vous supprimez le nom, la fonction [GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported) est insérée dans la table de dispatch d’interface. La méthode Get*PropertyName* fonction spécifie que la propriété est accessible en lecture.  
  
 **Set (fonction)**  
 Dispinterfaces MFC uniquement. Disponible uniquement si vous spécifiez **méthodes Get/Set** sous **type d’implémentation**. Définit le nom de la fonction pour définir la propriété. Par défaut, le nom de la fonction Set est défini au jeu de*PropertyName*. Vous pouvez modifier ce nom. Si vous supprimez le nom, la fonction [SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported) est insérée dans la table de dispatch d’interface. Le jeu de*PropertyName* fonction spécifie que la propriété est accessible en écriture.  
  
 **Type d’implémentation**  
 Dispinterfaces MFC uniquement. Indique comment implémenter la propriété que vous ajoutez.  
  
|Type d’implémentation|Description|  
|-------------------------|-----------------|  
|**Stock**|Spécifie une implémentation stock pour la propriété sélectionnée dans **nom de la propriété**. Valeur par défaut. Consultez [Propriétés Stock](../ide/stock-properties.md) pour plus d’informations.<br /><br /> Si vous spécifiez **Stock**, puis **type de propriété**, **type de paramètre**, et **nom de paramètre** sont estompés.|  
|**Variable membre**|Spécifie que la propriété est ajoutée en tant que variable membre. Vous pouvez ajouter des propriétés personnalisées ou la plupart des propriétés stock comme variables de membre. Vous ne pouvez pas spécifier **variable membre** pour **légende**, **hWnd**, et **texte** propriétés.<br /><br /> Fournit les noms par défaut sous **nom de la Variable** et **fonction de Notification**. Vous pouvez modifier ce nom.|  
|**Méthodes Get/Set**|Spécifie la propriété est ajoutée en tant que Get*PropertyName* et*PropertyName* fonctions, par défaut. Ces noms apparaissent sous **Get, fonction** et **définir la fonction**.<br /><br /> Vous pouvez modifier la valeur par défaut **type de propriété**, qui transmet une valeur pour la fonction Get. Vous pouvez spécifier des paramètres pour le **obtenir** et `Set` fonctions.|  
  
 **Get, fonction**  
 Pour les interfaces ATL. Définit la propriété est accessible en lecture ; Autrement dit, il crée le **obtenir** méthode pour extraire cette propriété de l’objet. Vous devez sélectionner **obtenir**, `Put`, ou les deux.  
  
 **Fonction Put**  
 Interfaces ATL uniquement. Définit la propriété accessible en écriture ; Autrement dit, il crée le `Put` (méthode), ou « placement », cette propriété de l’objet. Vous devez sélectionner **obtenir**, `Put`, ou les deux. Si vous sélectionnez cette option, vous pouvez choisir parmi deux façons d’implémenter la méthode :  
  
|Option|Description|  
|------------|-----------------|  
|**PropPut**|Le [PropPut](../windows/propput.md) fonction retourne une copie de l’objet. C’est la valeur par défaut et la méthode la plus courante pour rendre la propriété accessible en écriture.|  
|**PropPutRef**|Le [PropPutRef](../windows/propputref.md) fonction retourne une référence à l’objet et non la copie de l’objet lui-même. Envisagez d’utiliser cette option pour les objets, tels que des grandes structures ou les tableaux, ce qui peuvent dégrader l’initialisation.|  
  
 **Attributs de paramètre**  
 Interfaces ATL uniquement. Définit si le paramètre spécifié par **nom de paramètre** est **dans**, **hors**, les deux ou aucun.  
  
|Option|Description|  
|------------|-----------------|  
|**in**|Indique que le paramètre est passé à partir de la procédure appelante à la procédure appelée.|  
|**out**|Indique que le paramètre de pointeur est retourné à partir de la procédure appelée à la procédure appelante (du serveur au client).|  
  
 **Type de paramètre**  
 Définit le type de données du paramètre. Sélectionnez le type dans la liste.  
  
 **Nom du paramètre**  
 Définit le nom d’un paramètre que vous ajoutez pour la propriété, si la propriété possède des paramètres. Une fois que vous cliquez sur **ajouter**, le nom du paramètre s’affiche dans **liste de paramètres**.  
  
 **Liste de paramètres**  
 Affiche la liste des attributs à ajouter à la propriété. Chaque élément dans la liste se compose du nom de paramètre, le type de paramètre et les attributs. Utilisez **ajouter** et **supprimer** pour mettre à jour la liste.  
  
 **Ajouter**  
 Ajoute le paramètre que vous spécifiez dans **nom de paramètre** et **type de paramètre** à la **liste de paramètres**. Vous devez cliquer sur **ajouter** pour ajouter un paramètre à la liste.  
  
 **Supprimer**  
 Supprime le paramètre que vous sélectionnez dans **liste de paramètres**.  
  
 **Propriété par défaut**  
 Dispinterface MFC uniquement. Définit cette propriété en tant que la valeur par défaut pour l’interface. Une interface peut avoir uniquement une propriété par défaut ; une fois que vous spécifiez la propriété par défaut, pour toutes les autres propriétés que vous ajoutez à l’interface, cette case n’est pas disponible.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une propriété](../ide/adding-a-property-visual-cpp.md)   
 [Attributs IDL, Assistant Ajout de propriété](../ide/idl-attributes-add-property-wizard.md)   
 [Implémentation d’une Interface](../ide/implementing-an-interface-visual-cpp.md)