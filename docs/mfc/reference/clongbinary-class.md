---
title: "CLongBinary Class | Microsoft Docs"
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
  - "BLOB"
  - "CLongBinary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets binaires volumineux (BLOB)"
  - "objets binaires volumineux (BLOB), CLongBinary (classe)"
  - "CLongBinary (classe)"
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLongBinary Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Simplifies vous travaillez avec des données binaires très grandes objets \(BLOBs souvent appelé, ou « objets blobs »\) dans une base de données.  
  
## Syntaxe  
  
```  
class CLongBinary : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CLongBinary::CLongBinary](../Topic/CLongBinary::CLongBinary.md)|Construit un objet `CLongBinary`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CLongBinary::m\_dwDataLength](../Topic/CLongBinary::m_dwDataLength.md)|Contient la grandeur réelle en octets de l'objet de données dont le handle stocké dans `m_hData`.|  
|[CLongBinary::m\_hData](../Topic/CLongBinary::m_hData.md)|Contient un handle d' `HGLOBAL` windows à l'objet réel d'image.|  
  
## Notes  
 Par exemple, un champ d'enregistrement d'une table SQL peut contenir une bitmap représentant une image.  Un objet d' `CLongBinary` stocke un tel objet et maintient sa taille.  
  
> [!NOTE]
>  En général il est recommandé de meilleurs habitudes d'utiliser maintenant [CByteArray](../../mfc/reference/cbytearray-class.md) avec la fonction de [DFX\_Binary](../Topic/DFX_Binary.md) .  Vous pouvez toujours utiliser `CLongBinary`, mais en général `CByteArray` fournit des fonctionnalités sous Win32, car il n'y a plus de la limitation de taille produit avec `CByteArray`16 bits.  Ce conseil s'applique à la programmation avec DAO \(DAO\) ainsi que ODBC.  
  
 Pour utiliser un objet d' `CLongBinary` , déclarez les données membres de champ de type `CLongBinary` dans votre classe de recordset.  Ce membre est un membre inline de la classe de recordset et est construit lorsque le recordset est construit.  Une fois que l'objet d' `CLongBinary` construit, le mécanisme de l'record field exchange \(bulk RFX\) charge l'objet de données d'un champ de l'enregistrement en cours dans la source de données et l'enregistre vers l'enregistrement lorsque l'enregistrement est mis à jour.  RFX interroge la source de données pour la taille de l'objet blob, alloue de la mémoire pour lui \(via le membre d' `m_hData` de l'objet d' `CLongBinary` \), et stocke un handle d' `HGLOBAL` aux données dans `m_hData`.  RFX stocke également la grandeur réelle de l'objet de données dans le membre d' `m_dwDataLength` .  Utiliser les données dans l'objet via `m_hData`, en utilisant les mêmes techniques que vous utiliseriez normalement de manipuler les données stockées dans un handle d' `HGLOBAL` windows.  
  
 Lorsque vous perdez votre recordset, l'objet incorporé d' `CLongBinary` est également détruit, et son destructeur libère le handle de données d' `HGLOBAL` .  
  
 Pour plus d'informations sur de grands objets et l'utilisation d' `CLongBinary`, consultez les articles [recordset \(ODBC\)](../../data/odbc/recordset-odbc.md) et [recordset : Utilisation de grands éléments de données \(ODBC\)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## Configuration requise  
 **Header:** afxdb\_.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)