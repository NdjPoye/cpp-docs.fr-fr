---
title: "Assistant Ajout de variable membre | Microsoft Docs"
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
  - "vc.codewiz.variable.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ajout de variable membre (Assistant C++)"
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assistant Ajout de variable membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet Assistant ajoute une déclaration de variable membre au fichier d'en\-tête et, selon les options, il peut ajouter du code au fichier .cpp.  Lorsque vous avez ajouté la variable membre à l'aide de l'Assistant, vous pouvez modifier le code dans l'environnement de développement.  
  
 **Accès**  
 Définit l'accès à la variable membre.  Les modificateurs d'accès sont des mots clés spécifiant le type d'accès des autres classes à la variable membre.  Pour plus d'informations sur la spécification de l'accès, consultez [Contrôle d'accès des membres](../cpp/member-access-control-cpp.md).  Par défaut, le niveau d'accès à la variable membre a la valeur **public**.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 **Type de variable**  
 Définit le type de retour pour la variable membre que vous ajoutez.  
  
-   Si vous ajoutez une variable membre qui n'est pas un contrôle de boîte de dialogue, sélectionnez son type dans la liste des types disponibles.  
  
     Pour plus d'informations sur les types, consultez [Types fondamentaux](../cpp/fundamental-types-cpp.md).  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   Si vous ajoutez une variable membre pour un contrôle de boîte de dialogue, cette zone est remplie et contient le type d'objet retourné pour un contrôle ou une valeur.  Si vous sélectionnez **Contrôle**, la zone **Type de variable** spécifie la classe de base du contrôle que vous avez sélectionné dans la zone **ID de contrôle**.  Si le contrôle de boîte de dialogue contient une valeur et si vous sélectionnez **Valeur**, la zone **Type de variable** spécifie le type correct pour la valeur que le contrôle peut contenir.  Pour plus d'informations, consultez [Contrôles de boîtes de dialogue et types de variables](../ide/dialog-box-controls-and-variable-types.md).  
  
     Cette valeur dépend de votre sélection pour **ID de contrôle** et ne peut pas être modifiée.  
  
 **Nom de la variable**  
 Définit le nom de la variable membre que vous ajoutez.  Les variables membres commencent généralement par la chaîne d'identification « m\_, » proposée par défaut.  
  
 **Variable du contrôle**  
 Indique que la variable membre gère un contrôle à l'intérieur d'une boîte de dialogue intégrant la prise en charge de l'[échange et de la validation de données](../mfc/dialog-data-exchange-and-validation.md).  Pour plus d'informations, consultez [DoDataExchange](../Topic/CWnd::DoDataExchange.md).  Cette option est disponible uniquement pour les variables membres ajoutées aux classes dérivées de [CDialog](../mfc/reference/cdialog-class.md).  Activez cette case à cocher pour sélectionner les options **ID de contrôle** et **Type de contrôle**.  
  
 **ID de contrôle**  
 Définit l'ID de la variable de contrôle que vous ajoutez.  Sélectionnez dans la liste l'ID correspondant au type de contrôle pour lequel vous ajoutez la variable membre.  La liste est active uniquement si la case à cocher **Variable du contrôle** est activée. Elle se limite aux ID des contrôles déjà ajoutés à la boîte de dialogue.  Par exemple, l'ID de contrôle du bouton **OK** standard est **IDOK**.  
  
|Option|Description|  
|------------|-----------------|  
|**Contrôle**|Il s'agit de l'option par défaut pour le type de contrôle.  Elle gère le contrôle proprement dit et non son état ou son contenu \(cela peut être utile pour une zone de liste, une zone de liste déroulante ou une zone d'édition\).|  
|**Valeur**|Cette option est disponible uniquement pour les types de contrôles pouvant contenir une valeur \(par exemple une zone d'édition\) ou refléter un état \(par exemple une case à cocher\) et dont vous pouvez gérer la plage, le contenu ou l'état.  Pour plus d'informations, consultez [Contrôles de boîtes de dialogue et types de variables](../ide/dialog-box-controls-and-variable-types.md).|  
  
 **Catégorie**  
 Spécifie si la variable est basée sur un type de contrôle ou sur la valeur du contrôle.  
  
 **Type de contrôle**  
 Définit le type de contrôle ajouté.  Cette zone ne peut pas être modifiée.  Par exemple, un bouton possède le type de contrôle **BUTTON** et une zone de liste déroulante, le type de contrôle **COMBOBOX**.  Pour plus d'informations, consultez [Contrôles de boîtes de dialogue et types de variables](../ide/dialog-box-controls-and-variable-types.md).  
  
 **Caractères maxi**  
 Disponible uniquement si **Type de variable** a la valeur [CString](../atl-mfc-shared/reference/cstringt-class.md).  Indique le nombre maximal de caractères que le contrôle peut contenir.  
  
 **Valeur minimale**  
 Disponible uniquement si le type de variable est **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, [COLECurrency](../mfc/reference/colecurrency-class.md) ou [CTime](../atl-mfc-shared/reference/ctime-class.md).  Indique la plus petite valeur admise pour une échelle ou une plage de dates.  
  
 **Valeur maximale**  
 Disponible uniquement si le type de variable est **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, `COLECurrency` ou `CTime`.  Indique la plus grande valeur admise pour une échelle ou une plage de dates.  
  
 **fichier .h**  
 Pour les contrôles ActiveX dont les variables membres exigent une classe wrapper.  Définit le nom du fichier d'en\-tête auquel vous souhaitez ajouter la déclaration de classe.  
  
 **fichier .cpp**  
 Pour les contrôles ActiveX dont les variables membres exigent une classe wrapper.  Définit le nom du fichier d'implémentation auquel vous souhaitez ajouter la définition de classe.  
  
 **Commentaire**  
 Ajoute un commentaire dans le fichier d'en\-tête de la variable membre.  
  
## Voir aussi  
 [Ajout d'une variable membre](../ide/adding-a-member-variable-visual-cpp.md)