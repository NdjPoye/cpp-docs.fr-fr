---
title: Assistant Ajout de membre Variable | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.variable.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Variable Wizard [C++]
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3ae6a3aef4bdf774b5630a9bb0b2a0b49f7f29b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="add-member-variable-wizard"></a>Assistant Ajout de variable membre
Cet Assistant ajoute une déclaration de variable membre pour le fichier d’en-tête et, selon les options, il peut ajouter du code pour le fichier .cpp. Une fois que vous avez ajouté la variable membre à l’aide de l’Assistant, vous pouvez modifier le code dans l’environnement de développement.  
  
 **Accès**  
 Définit l’accès à la variable membre. Modificateurs d’accès sont des mots clés qui spécifient l’accès des autres classes à la variable membre. Consultez [le contrôle d’accès de membre](../cpp/member-access-control-cpp.md) pour plus d’informations sur la spécification de l’accès. Le niveau d’accès à la variable membre a la valeur **public** par défaut.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 **Type de variable**  
 Définit le type de retour pour la variable de membre que vous ajoutez.  
  
-   Si vous ajoutez une variable membre qui n’est pas un contrôle de boîte de dialogue, sélectionnez dans la liste des types disponibles.  
  
     Pour plus d’informations sur les types, consultez [Types fondamentaux](../cpp/fundamental-types-cpp.md).  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   Si vous ajoutez une variable membre pour un contrôle de boîte de dialogue, cette zone est renseignée avec le type de l’objet retourné pour un contrôle ou une valeur. Si vous sélectionnez **contrôle**, puis **le type de Variable** spécifie la classe de base du contrôle que vous sélectionnez dans la **ID de contrôle** boîte. Si le contrôle de boîte de dialogue peut contenir une valeur, et si vous sélectionnez **valeur**, puis **le type de Variable** Spécifie le type approprié pour la valeur que le contrôle peut contenir. Consultez [contrôles de boîte de dialogue et Types de variables](../ide/dialog-box-controls-and-variable-types.md) pour plus d’informations.  
  
     Cette valeur dépend de la sélection dans **ID de contrôle** et ne peut pas être modifié.  
  
 **Nom de variable**  
 Définit le nom de la variable de membre que vous ajoutez. Variables membres commencent généralement par la chaîne d’identification « m_ », ce qui vous est fournie par défaut.  
  
 **Variable de contrôle**  
 Indique que la variable membre gère un contrôle dans une boîte de dialogue [échange de données et la validation des données](../mfc/dialog-data-exchange-and-validation.md) prend en charge. Consultez [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) pour plus d’informations. Cette option est disponible uniquement pour les variables membres ajoutées aux classes dérivées de [CDialog](../mfc/reference/cdialog-class.md). Activez cette case pour activer la **ID de contrôle** et **type de contrôle** options.  
  
 **ID de contrôle**  
 Définit l’ID de la variable de contrôle que vous ajoutez. Dans la liste, sélectionnez l’ID pour le type de contrôle pour lequel vous souhaitez ajouter la variable membre. La liste est active uniquement lorsque le **la variable de contrôle** à cocher est activée, et il est limité à des ID pour les contrôles déjà ajoutés à la boîte de dialogue. Par exemple, pour la norme **OK** bouton, l’ID de contrôle est **IDOK**.  
  
|Option|Description|  
|------------|-----------------|  
|**Contrôle**|Cette option a la valeur par défaut pour le type de contrôle. Il gère le contrôle lui-même et pas l’état ou le contenu (que vous pouvez souhaiter faire avec une zone de liste, la zone de liste déroulante ou la zone d’édition) du contrôle.|  
|**Valeur**|Cette option est disponible uniquement pour les types de contrôles qui peuvent contenir une valeur (par exemple, une zone d’édition) ou refléter un état (par exemple, une case à cocher) et pour lequel vous pouvez gérer le contenu, plage ou l’état. Consultez [contrôles de boîte de dialogue et Types de variables](../ide/dialog-box-controls-and-variable-types.md) pour plus d’informations.|  
  
 **Catégorie**  
 Spécifie si la variable est basée sur un type de contrôle ou de la valeur du contrôle.  
  
 **Type de contrôle**  
 Définit le type de contrôle ajouté. Cette case n’est pas disponible pour le modifier. Par exemple, un bouton a le type de contrôle **bouton**, et une zone de liste modifiable a le type de contrôle **COMBOBOX**. Consultez [contrôles de boîte de dialogue et Types de variables](../ide/dialog-box-controls-and-variable-types.md) pour plus d’informations.  
  
 **Caractères max**  
 Disponible uniquement lorsque **le type de Variable** a la valeur [CString](../atl-mfc-shared/reference/cstringt-class.md). Indique le nombre maximal de caractères que le contrôle peut contenir.  
  
 **Valeur minimale**  
 Disponible uniquement si le type de variable est **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **octets**, **court**, [COLECurrency](../mfc/reference/colecurrency-class.md) ou [CTime](../atl-mfc-shared/reference/ctime-class.md). Indique la plus petite valeur acceptable pour une mise à l’échelle ou plage de dates.  
  
 **Valeur maximale**  
 Disponible uniquement si le type de variable est **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **octets**, **court**, `COLECurrency` ou `CTime`. Indique la valeur la plus élevée acceptable pour une mise à l’échelle ou plage de dates.  
  
 **fichier .h**  
 Pour les contrôles ActiveX, dont les variables membres exigent une classe wrapper. Définit le nom du fichier d’en-tête pour ajouter la déclaration de classe.  
  
 **fichier .cpp**  
 Pour les contrôles ActiveX, dont les variables membres exigent une classe wrapper. Définit le nom du fichier d’implémentation pour ajouter la définition de classe.  
  
 **Commentaire**  
 Fournit un commentaire dans le fichier d’en-tête pour la variable membre.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une Variable membre](../ide/adding-a-member-variable-visual-cpp.md)