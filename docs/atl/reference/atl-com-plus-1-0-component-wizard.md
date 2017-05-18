---
title: Assistant 1.0 composant ATL COM + | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding components
- ATL COM+ 1.0 Component Wizard
ms.assetid: 11670681-8671-4122-96a4-2e52f8dadce0
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2729975c5e823965f4f5c16d5bfe317ce10a3670
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="atl-com-10-component-wizard"></a>Assistant Composant COM+ 1.0 ATL
Utilisez cet Assistant pour ajouter un objet à votre projet qui prend en charge les services COM + 1.0, notamment les transactions.  
  
 Vous pouvez spécifier si l’objet prend en charge les interfaces doubles et l’automatisation. Vous pouvez également indiquer la prise en charge de l’interface d’informations d’erreur, contrôle évolué des objets, transactions et asynchrone message queuing.  
  
## <a name="remarks"></a>Notes  
 À partir de [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], le script d’inscription produit par cet Assistant inscrira ses composants COM sous **HKEY_CURRENT_USER** au lieu de **HKEY_LOCAL_MACHINE**. Pour modifier ce comportement, définissez la **inscrire le composant pour tous les utilisateurs** option de l’Assistant ATL.  
  
## <a name="names"></a>Noms  
 Spécifiez les noms de l’objet, interface et les classes à ajouter à votre projet. À l’exception de **nom court**, toutes les autres zones peuvent être modifiées indépendamment des autres. Si vous modifiez le texte **nom court**, la modification est répercutée dans les noms de toutes les autres zones de cette page. Si vous modifiez le **coclasse** nom de la section COM, la modification est répercutée dans le **Type** et **ProgID** zones, mais la **Interface** nom ne change pas. Ce comportement d’affectation de noms est conçu pour rendre tous les noms facilement identifiables pour vous lorsque vous développez votre contrôle.  
  
 **Nom court**  
 Définit le nom abrégé de l’objet. Le nom que vous fournissez détermine le `Class` et `Coclass` noms, le **fichier .cpp** et **fichier .h** noms, le **Interface** nom, le **Type** noms et le **ProgID**, sauf si vous modifiez ces champs individuellement.  
  
 **fichier .h**  
 Définit le nom du fichier d’en-tête pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom court**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant. Si vous choisissez un fichier existant, l’Assistant l’enregistrera pas à l’emplacement sélectionné jusqu'à ce que vous cliquez sur **Terminer** dans l’Assistant.  
  
 L’Assistant n’écrase pas un fichier. Si vous sélectionnez le nom d’un fichier existant, cliquez sur **Terminer**, l’Assistant vous invite à indiquer si la déclaration de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
 **(Classe)**  
 Définit le nom de la classe à créer. Ce nom est basé sur le nom que vous fournissez dans **nom court**, précédé de « C » (préfixe classique pour un nom de classe.  
  
 **fichier .cpp**  
 Définit le nom du fichier d’implémentation pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom court**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix. Le fichier n’est pas enregistré à l’emplacement sélectionné jusqu'à ce que vous cliquiez **Terminer** dans l’Assistant.  
  
 L’Assistant n’écrase pas un fichier. Si vous sélectionnez le nom d’un fichier existant, cliquez sur **Terminer**, l’Assistant vous invite à indiquer si l’implémentation de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
 **Par attributs**  
 Indique si l’objet utilise des attributs. Si vous ajoutez un objet à un projet ATL avec attributs, cette option est sélectionnée et non disponible pour modification. Autrement dit, vous pouvez ajouter uniquement les objets attribués à un projet créé avec prise en charge de l’attribut.  
  
 Si vous sélectionnez cette option pour un projet ATL ne prenant pas en charge les attributs, l’Assistant vous invite à spécifier si vous souhaitez ajouter la prise en charge de l’attribut pour le projet.  
  
 Les objets que vous ajoutez après avoir défini cette option sont désignés avec attributs par défaut (la case à cocher est activée). Vous pouvez désactiver cette case pour ajouter un objet qui n’utilise pas d’attributs.  
  
 Consultez la page [paramètres de l’Application, Assistant Projet ATL](../../atl/reference/application-settings-atl-project-wizard.md) et [mécanismes de base des attributs](../../windows/basic-mechanics-of-attributes.md) pour plus d’informations.  
  
### <a name="com"></a>COM  
 Fournit des informations sur les fonctionnalités COM pour l’objet.  
  
 **Coclasse**  
 Définit le nom de la classe de composant qui contient la liste des interfaces prises en charge par l’objet.  
  
> [!NOTE]
>  Si vous créez votre projet à l’aide d’attributs, ou si vous indiquez sur cette page de l’Assistant que le composant COM + 1.0 utilise des attributs, vous ne pouvez pas modifier cette option, car ATL n’inclut pas le `coclass` attribut.  
  
 **Type**  
 Définit la description de l’objet qui apparaîtra dans le Registre  
  
 **Interface**  
 Définit l’interface que vous créez pour votre objet. Cette interface contient vos méthodes personnalisées.  
  
 **ProgID**  
 Définit le nom que les conteneurs peuvent utiliser plutôt que le CLSID de l’objet.  
  
## <a name="see-also"></a>Voir aussi  
 [Composant ATL COM + 1.0](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)


