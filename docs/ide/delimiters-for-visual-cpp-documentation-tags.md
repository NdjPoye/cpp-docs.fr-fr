---
title: Délimiteurs pour les balises de Documentation Visual C++ | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- XML documentation, delimiters
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fe65dfec3befa15ffebde3d074081ee11364f4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="delimiters-for-visual-c-documentation-tags"></a>Délimiteurs pour les étiquettes de documentation Visual C++
L’utilisation de balises de documentation requiert des délimiteurs, qui indiquent au compilateur où un commentaire de documentation commence et se termine.  
  
 Vous pouvez utiliser les genres de délimiteurs ci-dessous avec les balises de documentation XML :  
  
 `///`  
 Il s’agit de l’écran qui est indiqué dans les exemples de documentation et utilisée par les modèles de projet Visual C++.  
  
 `/** */`  
 Il s’agit de délimiteurs multilignes.  
  
 Certaines mises en forme règles s’appliquent à l’aide de la `/** */` délimiteurs :  
  
-   Pour la ligne qui contienne le `/**` délimiteur, si le reste de la ligne est un espace blanc, la ligne n’est pas traitée pour les commentaires. Si le premier caractère est un espace blanc, est ignoré et le reste de la ligne est traité. Sinon, tout le texte de la ligne après le délimiteur `/**` est traité comme faisant partie du commentaire.  
  
-   Pour la ligne qui contienne le `*/` délimiteur, s’il existe uniquement des espaces jusqu'à la `*/` délimiteur, cette ligne est ignorée. Sinon, le texte de la ligne jusqu’au délimiteur `*/` est traité comme faisant partie du commentaire, conformément aux règles de critères spéciaux décrites dans la puce suivante.  
  
-   Pour les lignes après celle qui commence par le `/**` délimiteur, le compilateur recherche un modèle commun au début de chaque ligne se compose d’un espace blanc facultatif et un astérisque (`*`), suivi par plus d’un espace blanc facultatif. Si le compilateur trouve un ensemble commun de caractères au début de chaque ligne, il ignore ce modèle pour toutes les lignes situées après la `/**` délimiteur et peut éventuellement contenir la ligne qui contient le `*/` délimiteur.  
  
 Voici quelques exemples :  
  
-   La seule partie du commentaire suivant qui sera traitée est la ligne qui commence par `<summary>`. Les formats suivants de la deux balise produit les mêmes commentaires :  
  
    ```  
    /**  
    <summary>text</summary>   
    */  
    /** <summary>text</summary> */  
    ```  
  
-   Le compilateur applique un modèle de « * » pour ignorer au début des deuxième et troisième lignes.  
  
    ```  
    /**  
     * <summary>  
     *  text </summary>*/  
    ```  
  
-   Le compilateur trouve aucune séquence dans ce commentaire, car il n’existe aucun astérisque sur la deuxième ligne. Par conséquent, tout le texte sur les deuxième et troisième lignes, jusqu’au délimiteur le `*/`, est traité comme une partie du commentaire.  
  
    ```  
    /**  
     * <summary>  
       text </summary>*/  
    ```  
  
-   Le compilateur ne trouve aucun modèle dans ce commentaire pour deux raisons. Tout d’abord, il n’existe aucune ligne qui commence par un nombre constant d’espaces avant l’astérisque. Ensuite, la cinquième ligne commence par une tabulation, qui ne correspond pas à des espaces. Par conséquent, tout le texte de la deuxième ligne jusqu'à ce que le `*/` sera traitée comme étant le commentaire.  
  
    ```  
    /**  
      * <summary>  
      * text   
     *  text2  
       *  </summary>  
    */  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)