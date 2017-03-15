---
title: Classe de CD2DMesh | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DMesh
- CD2DMesh
dev_langs:
- C++
helpviewer_keywords:
- CD2DMesh class
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
caps.latest.revision: 17
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 78461adeaa0671b146ccb48f4e9145cbdceeb8cf
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dmesh-class"></a>CD2DMesh, classe
Wrapper pour ID2D1Mesh.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DMesh : public CD2DResource;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DMesh::CD2DMesh](#cd2dmesh)|Construit un objet CD2DMesh.|  
|[CD2DMesh :: ~ CD2DMesh](#_dtorcd2dmesh)|Destructeur. Appelé lorsqu’un objet de maillage D2D est détruit.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DMesh::Attach](#attach)|Attache existant à l’objet interface de la ressource|  
|[CD2DMesh::Create](#create)|Crée un CD2DMesh. (Substitue [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DMesh::Destroy](#destroy)|Détruit un objet CD2DMesh. (Substitue [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DMesh::Detach](#detach)|Détache l’interface de la ressource à partir de l’objet|  
|[CD2DMesh::Get](#get)|Renvoie l’interface ID2D1Mesh|  
|[CD2DMesh::IsValid](#isvalid)|Vérifie la validité des ressources (substitue [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DMesh::Open](#open)|Ouvre le maillage pour le remplissage.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DMesh::operator ID2D1Mesh *](#operator_id2d1mesh_star)|Renvoie l’interface ID2D1Mesh|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DMesh::m_pMesh](#m_pmesh)|Pointeur vers un ID2D1Mesh.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DMesh`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dmesha--cd2dmeshcd2dmesh"></a><a name="_dtorcd2dmesh"></a>CD2DMesh :: ~ CD2DMesh  
 Destructeur. Appelé lorsqu’un objet de maillage D2D est détruit.  
  
```  
virtual ~CD2DMesh();
```  
  
##  <a name="a-nameattacha--cd2dmeshattach"></a><a name="attach"></a>CD2DMesh::Attach  
 Attache existant à l’objet interface de la ressource  
  
```  
void Attach(ID2D1Mesh* pResource);
```  
  
### <a name="parameters"></a>Paramètres  
 `pResource`  
 Interface de la ressource existante. Ne peut pas être NULL  
  
##  <a name="a-namecd2dmesha--cd2dmeshcd2dmesh"></a><a name="cd2dmesh"></a>CD2DMesh::CD2DMesh  
 Construit un objet CD2DMesh.  
  
```  
CD2DMesh(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentTarget`  
 Pointeur vers la cible de rendu.  
  
 `bAutoDestroy`  
 Indique que l’objet sera détruit par le propriétaire (pParentTarget).  
  
##  <a name="a-namecreatea--cd2dmeshcreate"></a><a name="create"></a>CD2DMesh::Create  
 Crée un CD2DMesh.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRenderTarget`  
 Pointeur vers la cible de rendu.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne S_OK. Sinon, elle retourne un code d’erreur HRESULT.  
  
##  <a name="a-namedestroya--cd2dmeshdestroy"></a><a name="destroy"></a>CD2DMesh::Destroy  
 Détruit un objet CD2DMesh.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dmeshdetach"></a><a name="detach"></a>CD2DMesh::Detach  
 Détache l’interface de la ressource à partir de l’objet  
  
```  
ID2D1Mesh* Detach();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’interface de la ressource détachée.  
  
##  <a name="a-namegeta--cd2dmeshget"></a><a name="get"></a>CD2DMesh::Get  
 Renvoie l’interface ID2D1Mesh  
  
```  
ID2D1Mesh* Get();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1Mesh ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="a-nameisvalida--cd2dmeshisvalid"></a><a name="isvalid"></a>CD2DMesh::IsValid  
 Vérifications de validité des ressources  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la ressource est valide ; Sinon, FALSE.  
  
##  <a name="a-namempmesha--cd2dmeshmpmesh"></a><a name="m_pmesh"></a>CD2DMesh::m_pMesh  
 Pointeur vers un ID2D1Mesh.  
  
```  
ID2D1Mesh* m_pMesh;  
```  
  
##  <a name="a-nameopena--cd2dmeshopen"></a><a name="open"></a>CD2DMesh::Open  
 Ouvre le maillage pour le remplissage.  
  
```  
ID2D1TessellationSink* Open();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un ID2D1TessellationSink utilisé pour remplir le maillage.  
  
##  <a name="a-nameoperatorid2d1meshstara--cd2dmeshoperator-id2d1mesh"></a><a name="operator_id2d1mesh_star"></a>CD2DMesh::operator ID2D1Mesh *  
 Renvoie l’interface ID2D1Mesh  
  
```  
operator ID2D1Mesh*();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1Mesh ou NULL si l’objet n’est pas encore initialisé.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

