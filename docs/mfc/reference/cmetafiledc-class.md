---
title: Classe CMetaFileDC | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMetaFileDC
dev_langs:
- C++
helpviewer_keywords:
- CMetaFileDC class
- Windows metafiles [C++]
- metafiles, implementing
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4bff4d7601c4ffbc6fe5cbe73f5e057b79abf1e5
ms.lasthandoff: 02/24/2017

---
# <a name="cmetafiledc-class"></a>CMetaFileDC (classe)
Implémente un métafichier Windows, qui contient une séquence de commandes SQL GDI (Graphics Device Interface) que vous pouvez relire pour créer une image ou du texte voulu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMetaFileDC : public CDC  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|Construit un objet `CMetaFileDC`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMetaFileDC::Close](#close)|Ferme le contexte de périphérique et crée un handle de métafichier.|  
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|Ferme un contexte de périphérique de métafichier amélioré et crée un handle du métafichier amélioré.|  
|[CMetaFileDC::Create](#create)|Crée le contexte de périphérique de métafichier Windows et l’attache à le `CMetaFileDC` objet.|  
|[CMetaFileDC::CreateEnhanced](#createenhanced)|Crée un contexte de périphérique de métafichier pour un métafichier de format amélioré.|  
  
## <a name="remarks"></a>Remarques  
 Pour implémenter un métafichier Windows, commencez par créer un `CMetaFileDC` objet. Appeler le `CMetaFileDC` constructeur, puis appelez le [créer](#create) fonction membre, ce qui crée un contexte de périphérique de métafichier Windows et l’attache à le `CMetaFileDC` objet.  
  
 Envoyez ensuite le `CMetaFileDC` la séquence de l’objet `CDC` commandes GDI que vous prévoyez pour la relecture. Uniquement les commandes GDI créent le résultat, tel que `MoveTo` et `LineTo`, peut être utilisé.  
  
 Une fois que vous avez envoyé les commandes souhaitées à un métafichier, appelez le **fermer** fonction membre, ce qui ferme les contextes de périphérique de métafichier et retourne un handle de métafichier. Puis de supprimer le `CMetaFileDC` objet.  
  
 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) pouvez ensuite utiliser le handle de métafichier pour lire le métafichier à plusieurs reprises. Le métafichier également peut être manipulé par les fonctions de Windows telles que [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480), qui copie un métafichier sur le disque.  
  
 Une fois le métafichier n’est plus nécessaire, supprimez-le de la mémoire avec le [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) fonction Windows.  
  
 Vous pouvez également implémenter le `CMetaFileDC` de l’objet afin qu’il puisse gérer les appels de sortie et attribut tel que les appels GDI `GetTextExtent`. Tel un métafichier est plus flexible et plus facilement réemployer générale des codes GDI, qui se compose souvent une combinaison d’appels de sortie et d’attribut. Le `CMetaFileDC` classe hérite des deux contextes de périphérique, `m_hDC` et `m_hAttribDC`, à partir de `CDC`. Le `m_hDC` contexte de périphérique gère tous les [CDC](../../mfc/reference/cdc-class.md) GDI sortie des appels et le `m_hAttribDC` contexte de périphérique gère tous les `CDC` GDI attribut appelle. En règle générale, les contextes de deux périphérique font référence au même périphérique. Dans le cas de `CMetaFileDC`, le contrôleur de domaine de l’attribut est défini sur **NULL** par défaut.  
  
 Créer un deuxième contexte de périphérique qui pointe vers l’écran, une imprimante ou un périphérique autre qu’un métafichier, puis appelez le `SetAttribDC` fonction membre pour associer le nouveau contexte de périphérique avec `m_hAttribDC`. Appels GDI pour plus d’informations seront désormais dirigées vers le nouveau `m_hAttribDC`. Sortie GDI appelle passera à `m_hDC`, qui représente le métafichier.  
  
 Pour plus d’informations sur `CMetaFileDC`, consultez [contextes de périphérique](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAPTURE DE DONNÉES MODIFIÉES](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxext.h  
  
##  <a name="a-nameclosea--cmetafiledcclose"></a><a name="close"></a>CMetaFileDC::Close  
 Ferme le contexte de périphérique de métafichier et crée un handle de métafichier de Windows qui peut être utilisé pour lire le métafichier à l’aide de la [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) fonction membre.  
  
```  
HMETAFILE Close();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valide **HMETAFILE** si la fonction réussit ; sinon **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Le handle de métafichier Windows peut servir à manipuler le métafichier avec les fonctions Windows telles que [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480).  
  
 Supprimer le métafichier après utilisation en appelant Windows [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) (fonction).  
  
##  <a name="a-namecloseenhanceda--cmetafiledccloseenhanced"></a><a name="closeenhanced"></a>CMetaFileDC::CloseEnhanced  
 Ferme un contexte de périphérique de métafichier amélioré et retourne un handle qui identifie un métafichier de format amélioré.  
  
```  
HENHMETAFILE CloseEnhanced();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Handle d’un métafichier amélioré, en cas de réussite ; dans le cas contraire **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Une application peut utiliser le handle de métafichier amélioré retourné par cette fonction pour effectuer les tâches suivantes :  
  
-   Afficher une image stockée dans un métafichier amélioré  
  
-   Créer des copies du métafichier amélioré  
  
-   Énumérer, modifier ou copier des enregistrements dans le métafichier amélioré  
  
-   Récupérer une description facultative du contenu du métafichier depuis l’en-tête du métafichier amélioré  
  
-   Récupérer une copie de l’en-tête du métafichier amélioré  
  
-   Récupérer une copie binaire du métafichier amélioré  
  
-   Énumérer les couleurs de la palette facultative  
  
-   Convertir un métafichier de format amélioré dans un métafichier de format Windows  
  
 Lorsque l’application n’a plus besoin du handle de métafichier amélioré, elle doit libérer le handle en appelant Win32 **DeleteEnhMetaFile** (fonction).  
  
##  <a name="a-namecmetafiledca--cmetafiledccmetafiledc"></a><a name="cmetafiledc"></a>CMetaFileDC::CMetaFileDC  
 Construire un `CMetaFileDC` objet en deux étapes.  
  
```  
CMetaFileDC();
```  
  
### <a name="remarks"></a>Remarques  
 Tout d’abord, appelez `CMetaFileDC`, puis appelez **créer**, ce qui crée le contexte de périphérique de métafichier Windows et l’attache à le `CMetaFileDC` objet.  
  
##  <a name="a-namecreatea--cmetafiledccreate"></a><a name="create"></a>CMetaFileDC::Create  
 Construire un `CMetaFileDC` objet en deux étapes.  
  
```  
BOOL Create(LPCTSTR lpszFilename = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszFilename*  
 Pointe vers une chaîne de caractères se terminant par null. Spécifie le nom de fichier du métafichier à créer. Si *lpszFilename* est **NULL**, un métafichier en mémoire est créé.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Tout d’abord, appelez le constructeur `CMetaFileDC`, puis appelez **créer**, ce qui crée le contexte de périphérique de métafichier Windows et l’attache à le `CMetaFileDC` objet.  
  
##  <a name="a-namecreateenhanceda--cmetafiledccreateenhanced"></a><a name="createenhanced"></a>CMetaFileDC::CreateEnhanced  
 Crée un contexte de périphérique pour un métafichier de format amélioré.  
  
```  
BOOL CreateEnhanced(
    CDC* pDCRef,  
    LPCTSTR lpszFileName,  
    LPCRECT lpBounds,  
    LPCTSTR lpszDescription);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDCRef`  
 Identifie une unité de référence pour le métafichier amélioré.  
  
 `lpszFileName`  
 Pointe vers une chaîne de caractères se terminant par null. Spécifie le nom de fichier pour le métafichier amélioré doit être créé. Si ce paramètre est **NULL**, métafichier amélioré est basée sur la mémoire et son contenu perdu lorsque l’objet est détruit ou lorsque Win32 **DeleteEnhMetaFile** fonction est appelée.  
  
 `lpBounds`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure de données ou un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui spécifie les dimensions dans **HIMETRIC** unités (par incréments de.01 millimètres) de l’image à stocker dans le métafichier amélioré.  
  
 `lpszDescription`  
 Pointe vers une chaîne terminée par zéro qui spécifie le nom de l’application qui a créé l’image, ainsi que le titre de l’image.  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle du contexte de périphérique de métafichier amélioré, en cas de réussite ; dans le cas contraire **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Ce contrôleur de domaine peut être utilisé pour stocker une image indépendante du périphérique.  
  
 Windows utilise l’appareil de référence identifié par le `pDCRef` paramètre pour enregistrer les unités de l’appareil sur lequel une image s’affiche à l’origine et la résolution. Si le `pDCRef` paramètre est **NULL**, elle utilise le périphérique d’affichage actuelle pour référence.  
  
 Les membres de gauche et supérieur de la `RECT` structure de données vers laquelle pointe le `lpBounds` paramètre doit être plus petite que les membres de droite et en bas, respectivement. Points le long des bords du rectangle sont inclus dans l’image. Si `lpBounds` est **NULL**, l’interface graphique (GDI) calcule les dimensions du rectangle plus petit qui entoure l’image dessinée par l’application. Le `lpBounds` paramètre doit être fourni lorsque cela est possible.  
  
 La chaîne pointée par la `lpszDescription` paramètre doit contenir un caractère null entre le nom de l’application et le nom de l’image et doit se terminer par deux caractères null — par exemple, « XYZ graphiques Editor\0Bald Eagle\0\0, « où \0 représente le caractère null. Si `lpszDescription` est **NULL**, il n’existe aucune entrée correspondante dans l’en-tête du métafichier amélioré.  
  
 Applications utilisent le contrôleur de domaine créé par cette fonction pour stocker une image de graphique dans un métafichier amélioré. Le handle de ce contrôleur de domaine peut être passé aux fonctions GDI.  
  
 Une fois une application stocke une image dans un métafichier amélioré, il peut afficher l’image sur tout périphérique de sortie en appelant le `CDC::PlayMetaFile` (fonction). Lorsque vous affichez l’image, Windows utilise le rectangle vers lequel pointé le `lpBounds` paramètre et les données de résolution de l’appareil de référence pour positionner et redimensionner l’image. Le contexte de périphérique retourné par cette fonction contient les mêmes attributs par défaut associés à un nouveau contrôleur de domaine.  
  
 Les applications doivent utiliser Win32 **GetWinMetaFileBits** fonction pour convertir un métafichier amélioré à l’ancien format de métafichier Windows.  
  
 Le nom de fichier pour le métafichier amélioré doit utiliser le. Extension EMF.  
  
## <a name="see-also"></a>Voir aussi  
 [CDC (classe)](../../mfc/reference/cdc-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




