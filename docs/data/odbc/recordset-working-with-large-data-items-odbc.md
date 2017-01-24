---
title: "Recordset&#160;: utilisation d&#39;&#233;l&#233;ments de donn&#233;es volumineux (ODBC) | Microsoft Docs"
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
  - "objets binaires volumineux"
  - "objets binaires volumineux (BLOB), recordsets"
  - "CLongBinary (classe), utiliser dans des recordsets"
  - "ODBC (recordsets), objets binaires volumineux"
  - "recordsets, objets binaires volumineux"
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: utilisation d&#39;&#233;l&#233;ments de donn&#233;es volumineux (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La présente rubrique s'applique aux classes ODBC MFC et aux classes DAO MFC.  
  
> [!NOTE]
>  Si vous utilisez les classes DAO MFC, gérez les éléments de données volumineux avec la classe [CByteArray](../../mfc/reference/cbytearray-class.md) plutôt qu'avec la classe [CLongBinary](../../mfc/reference/clongbinary-class.md).  Si vous utilisez les classes ODBC MFC avec l'extraction de lignes en bloc, utilisez `CLongBinary` de préférence à `CByteArray`.  Pour plus d'informations sur l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Imaginons que votre base de données puisse stocker des éléments de données volumineux, comme les bitmaps \(photos du personnel, cartes, photos de produits, objets OLE, etc.\).  Ce type de données est souvent désigné par le terme d'objet BLOB \(Binary Large OBject\) pour les raisons suivantes:  
  
-   Chaque valeur de champ est volumineuse.  
  
-   Contrairement aux données numériques et autres types de données simples, il est impossible de prédire leur taille.  
  
-   Les données sont sans forme du point de vue de votre programme.  
  
 La présente rubrique explique quel type de prise en charge fournissent les classes de base de données pour travailler avec ces objets.  
  
##  <a name="_core_managing_large_objects"></a> Gestion d'objets volumineux  
 Les recordsets permettent de résoudre de deux façons la difficulté liée à la gestion des objets BLOB.  Vous pouvez utiliser les classes [CByteArray](../../mfc/reference/cbytearray-class.md) ou [CLongBinary](../../mfc/reference/clongbinary-class.md).  En règle générale, c'est `CByteArray` qui recueille la majorité des suffrages.  
  
 `CByteArray` requiert plus de charge que `CLongBinary` mais offre plus de possibilités, comme décrit dans [Classe CByteArray](#_core_the_cbytearray_class).  `CLongBinary` est décrit brièvement dans [Classe CLongBinary](#_core_the_clongbinary_class).  
  
 Pour plus d'informations sur l'utilisation de `CByteArray` dans le cas d'éléments de données volumineux, consultez la [Note technique 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_cbytearray_class"></a> Classe CByteArray  
 `CByteArray` est l'une des classes de collection MFC.  Un objet `CByteArray` stocke un tableau dynamique d'octets, et la taille d'un tableau peut être augmentée si nécessaire.  La classe fournit un accès rapide par index comme avec les tableaux intégrés C\+\+.  Les objets `CByteArray` peuvent être sérialisés et faire l'objet d'un dump à des fins de diagnostic.  La classe fournit les fonctions membres permettant d'obtenir et de définir les octets spécifiés, d'insérer ou d'ajouter des octets, et de supprimer un octet ou leur totalité.  Ces fonctions facilitent l'analyse des données binaires.  Par exemple, si l'objet binaire est un objet OLE, il se peut que vous ayez à passer par des octets d'en\-tête pour atteindre l'objet lui\-même.  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a> Utilisation de CByteArray dans les recordsets  
 En attribuant à un membre de données de type champ de votre enregistrement le type `CByteArray`, vous fournissez une base fixe à partir de laquelle [RFX](../../data/odbc/record-field-exchange-rfx.md) peut gérer le transfert d'un tel objet entre votre recordset et la source de données, et grâce à laquelle vous pouvez manipuler les données à l'intérieur de l'objet.  RFX a besoin d'un emplacement particulier pour les données récupérées, et vous\-même avez besoin d'un moyen d'accès aux données sous\-jacentes.  
  
 Pour plus d'informations sur l'utilisation de `CByteArray` dans le cas d'éléments de données volumineux, consultez la [Note technique 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_clongbinary_class"></a> Classe CLongBinary  
 Un objet [CLongBinary](../../mfc/reference/clongbinary-class.md) n'est qu'un simple shell abritant le handle `HGLOBAL` d'un bloc de stockage alloué dans le tas.  Quand RFX lie une colonne de table contenant un objet binaire volumineux, il alloue le handle `HGLOBAL` quand il doit transférer les données vers le recordset et stocke le handle dans le champ `CLongBinary` du recordset.  
  
 À votre tour, vous utilisez le handle `HGLOBAL`, `m_hData`, pour travailler avec les données elles\-mêmes, les utilisant comme vous le feriez pour toute donnée du handle.  C'est sur ce point que [CByteArray](../../mfc/reference/cbytearray-class.md) offre des capacités supplémentaires.  
  
> [!CAUTION]
>  Les objets CLongBinary ne peuvent pas servir de paramètres dans les appels de fonction.  De plus, leur implémentation, qui appelle **::SQLGetData**, ralentit nécessairement les performances de défilement dans le cas d'un instantané affichable par ce biais\-là.  Cela peut également être vrai quand vous utilisez vous\-même un appel **::SQLGetData** pour récupérer les colonnes de schéma dynamiques.  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : calculs de totaux et autres résultats de regroupement \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)