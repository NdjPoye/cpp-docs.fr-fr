---
title: CPen (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
dev_langs:
- C++
helpviewer_keywords:
- HPEN
- CPen class
- pens, MFC
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: 20
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
ms.openlocfilehash: edea12c84a8f39161acbf367360fd86a1ff19998
ms.lasthandoff: 02/24/2017

---
# <a name="cpen-class"></a>CPen (classe)
Encapsule un stylet GDI (Graphics Device Interface) Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CPen : public CGdiObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPen::CPen](#cpen)|Construit un objet `CPen`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPen::CreatePen](#createpen)|Crée un stylet logique cosmétique ou géométrique avec le style spécifié, la largeur et les attributs de forme et l’attache à le `CPen` objet.|  
|[CPen::CreatePenIndirect](#createpenindirect)|Crée un stylet avec le style, la largeur et la couleur donnée un [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) de la structure et l’attache à le `CPen` objet.|  
|[CPen::FromHandle](#fromhandle)|Retourne un pointeur vers un `CPen` en fonction d’une fenêtre de l’objet `HPEN`.|  
|[CPen::GetExtLogPen](#getextlogpen)|Obtient un [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) structure sous-jacente.|  
|[CPen::GetLogPen](#getlogpen)|Obtient un [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) structure sous-jacente.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPen::operator HPEN](#operator_hpen)|Retourne le handle Windows associé à le `CPen` objet.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations sur l’utilisation de `CPen`, consultez [objets graphiques](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="cpen"></a>CPen::CPen  
 Construit un objet `CPen`.  
  
```  
CPen();

 
CPen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
CPen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nPenStyle`  
 Spécifie le style du stylet. Ce paramètre dans la première version du constructeur peut être une des valeurs suivantes :  
  
- **PS_SOLID** crée un stylet continu.  
  
- **PS_DASH** crée un stylet en pointillés. Valide uniquement lorsque la largeur du stylet est 1 ou moins, appareil unités.  
  
- **PS_DOT** crée un stylet en pointillés. Valide uniquement lorsque la largeur du stylet est 1 ou moins, appareil unités.  
  
- **PS_DASHDOT** crée un stylet avec des points et des tirets alternés. Valide uniquement lorsque la largeur du stylet est 1 ou moins, appareil unités.  
  
- **PS_DASHDOTDOT** crée un stylet avec deux points et des tirets alternés. Valide uniquement lorsque la largeur du stylet est 1 ou moins, appareil unités.  
  
- **PS_NULL** crée un stylet null.  
  
- **PS_INSIDEFRAME** crée un stylet qui dessine une ligne dans le cadre des formes fermées produites par les fonctions de sortie Windows GDI qui spécifient un rectangle englobant (par exemple, le **Ellipse**, **Rectangle**, `RoundRect`, `Pie`, et `Chord` les fonctions membres). Lorsque ce style est utilisé avec les fonctions de sortie Windows GDI qui ne spécifient pas un rectangle englobant (par exemple, le `LineTo` fonction membre), la zone de dessin du stylet n’est pas limitée par un frame.  
  
 La deuxième version de la `CPen` constructeur spécifie une combinaison de type, le style, extrémité de fin et les attributs de jointure. Les valeurs de chaque catégorie doivent être combinées à l’aide de l’opérateur OR (|). Le type du stylet peut être une des valeurs suivantes :  
  
- **PS_GEOMETRIC** crée un stylet géométrique.  
  
- **PS_COSMETIC** crée un stylet.  
  
     La deuxième version de la `CPen` constructeur ajoute les styles suivants de stylet pour `nPenStyle`:  
  
- **PS_ALTERNATE** crée un stylet qui définit tous les autres pixels. (Ce style s’applique uniquement aux stylos cosmétiques.)  
  
- **PS_USERSTYLE** crée un stylet qui utilise un tableau de style fourni par l’utilisateur.  
  
     L’extrémité de fin peut être une des valeurs suivantes :  
  
- **PS_ENDCAP_ROUND** extrémités sont arrondies.  
  
- **PS_ENDCAP_SQUARE** extrémités sont carrées.  
  
- **PS_ENDCAP_FLAT** extrémités sont fixes.  
  
     La jointure peut être une des valeurs suivantes :  
  
- **PS_JOIN_BEVEL** jointures sont en relief.  
  
- **PS_JOIN_MITER** jointures sont entre elles forment lorsqu’ils se trouvent dans la limite actuelle définie par le [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076) (fonction). Si la jointure dépasse cette limite, il est en relief.  
  
- **PS_JOIN_ROUND** les jointures sont arrondis.  
  
 `nWidth`  
 Spécifie la largeur du stylet.  
  
-   Pour la première version du constructeur, si cette valeur est 0, la largeur en unités de périphérique est toujours 1 pixel, quel que soit le mode de mappage.  
  
-   Pour la deuxième version du constructeur, si `nPenStyle` est **PS_GEOMETRIC**, la largeur est exprimée en unités logiques. Si `nPenStyle` est **PS_COSMETIC**, la largeur doit être définie sur 1.  
  
 `crColor`  
 Contient une couleur RVB pour le stylet.  
  
 `pLogBrush`  
 Pointe vers une `LOGBRUSH` structure. Si `nPenStyle` est **PS_COSMETIC**, la `lbColor` membre de la `LOGBRUSH` structure spécifie la couleur du stylet et le `lbStyle` membre de la `LOGBRUSH` structure doit avoir la valeur **BS_SOLID**. Si `nPenStyle` est **PS_GEOMETRIC**, tous les membres doivent être utilisés pour spécifier les attributs de pinceau du stylet.  
  
 `nStyleCount`  
 Spécifie la longueur, en unités de double de le `lpStyle` tableau. Cette valeur doit être zéro si `nPenStyle` n’est pas **PS_USERSTYLE**.  
  
 `lpStyle`  
 Pointe vers un tableau de valeurs de DWORD. La première valeur spécifie la longueur du premier tiret dans un style défini par l’utilisateur, la deuxième valeur spécifie la longueur du premier espace et ainsi de suite. Ce pointeur doit être **NULL** si `nPenStyle` n’est pas **PS_USERSTYLE**.  
  
### <a name="remarks"></a>Remarques  
 Si vous utilisez le constructeur sans arguments, vous devez initialiser résultant `CPen` de l’objet avec la `CreatePen`, `CreatePenIndirect`, ou `CreateStockObject` les fonctions membres.  
  
 Si vous utilisez le constructeur qui prend des arguments, aucune initialisation supplémentaire n’est nécessaire. Le constructeur avec des arguments peut lever une exception si des erreurs surviennent, tandis que le constructeur sans arguments échoue jamais.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#99;](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="createpen"></a>CPen::CreatePen  
 Crée un stylet logique cosmétique ou géométrique avec le style spécifié, la largeur et les attributs de forme et l’attache à le `CPen` objet.  
  
```  
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nPenStyle`  
 Spécifie le style pour le stylet. Pour obtenir la liste des valeurs possibles, consultez la `nPenStyle` paramètre dans le [CPen](#cpen) constructeur.  
  
 `nWidth`  
 Spécifie la largeur du stylet.  
  
-   Pour la première version de `CreatePen`, si cette valeur est 0, la largeur en unités de périphérique est toujours 1 pixel, quel que soit le mode de mappage.  
  
-   Pour la deuxième version de `CreatePen`si `nPenStyle` est **PS_GEOMETRIC**, la largeur est exprimée en unités logiques. Si `nPenStyle` est **PS_COSMETIC**, la largeur doit être définie sur 1.  
  
 `crColor`  
 Contient une couleur RVB pour le stylet.  
  
 `pLogBrush`  
 Pointe vers une [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) structure. Si `nPenStyle` est **PS_COSMETIC**, la **lbColor** membre de la `LOGBRUSH` structure spécifie la couleur du stylet et le `lbStyle` membre de la `LOGBRUSH` structure doit avoir la valeur **BS_SOLID**. Si **nPenStyle** est **PS_GEOMETRIC**, tous les membres doivent être utilisés pour spécifier les attributs de pinceau du stylet.  
  
 `nStyleCount`  
 Spécifie la longueur, en unités de double de le `lpStyle` tableau. Cette valeur doit être zéro si `nPenStyle` n’est pas **PS_USERSTYLE**.  
  
 `lpStyle`  
 Pointe vers un tableau de valeurs de DWORD. La première valeur spécifie la longueur du premier tiret dans un style défini par l’utilisateur, la deuxième valeur spécifie la longueur du premier espace et ainsi de suite. Ce pointeur doit être **NULL** si `nPenStyle` n’est pas **PS_USERSTYLE**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération réussit, ou zéro si la méthode échoue.  
  
### <a name="remarks"></a>Remarques  
 La première version de `CreatePen` Initialise un stylet avec le style spécifié, la largeur et la couleur. Le stylet peut être sélectionné par la suite que le stylet actuel pour n’importe quel contexte de périphérique.  
  
 Stylets qui ont une largeur supérieure à 1 pixel doit toujours avoir soit le **PS_NULL**, **PS_SOLID**, ou **PS_INSIDEFRAME** style.  
  
 Si le stylet a la **PS_INSIDEFRAME** style et une couleur qui ne correspond pas à une couleur de la table logique, le stylet est dessiné avec une couleur dégradée. Le **PS_SOLID** style de stylet ne peut pas être utilisé pour créer un stylet avec une couleur dégradée. Le style **PS_INSIDEFRAME** est identique à **PS_SOLID** si la largeur du stylet est inférieur ou égal à 1.  
  
 La deuxième version de `CreatePen` Initialise un stylet logique cosmétique ou géométrique sont spécifiés, de largeur, style et attributs du pinceau. La largeur d’un stylet est toujours 1. la largeur d’un stylet géométrique est toujours spécifiée en unités universelles. Une fois une application crée un stylet logique, elle peut sélectionner ce stylet dans un contexte de périphérique en appelant le [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) (fonction). Après avoir sélectionné un stylet dans un contexte de périphérique, il peut être utilisé pour dessiner des lignes et des courbes.  
  
-   Si `nPenStyle` est **PS_COSMETIC** et **PS_USERSTYLE**, les entrées de le `lpStyle` tableau spécifient les longueurs des tirets et des espaces dans les unités de style. Une unité de style est définie par le périphérique dans lequel le stylet est utilisé pour dessiner une ligne.  
  
-   Si `nPenStyle` est **PS_GEOMETRIC** et **PS_USERSTYLE**, les entrées de le `lpStyle` tableau spécifient les longueurs des tirets et des espaces en unités logiques.  
  
-   Si `nPenStyle` est **PS_ALTERNATE**, l’unité de style est ignorée et tous les autres pixels est défini.  
  
 Lorsqu’une application ne requiert plus un stylet donné, il doit appeler la [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) membre de fonction ou de détruire le `CPen` pour la ressource n’est plus en cours d’utilisation de l’objet. Une application ne doit pas supprimer un stylet lorsque le stylet est sélectionné dans un contexte de périphérique.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[100 NVC_MFCDocView](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="createpenindirect"></a>CPen::CreatePenIndirect  
 Initialise un stylet qui a le style, la largeur et la couleur indiquée dans la structure vers laquelle pointe `lpLogPen`.  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpLogPen`  
 Pointe vers le Windows [LOGPEN](../../mfc/reference/logpen-structure.md) structure qui contient des informations sur le stylet.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Stylets qui ont une largeur supérieure à 1 pixel doit toujours avoir soit le **PS_NULL**, **PS_SOLID**, ou **PS_INSIDEFRAME** style.  
  
 Si le stylet a la **PS_INSIDEFRAME** style et une couleur qui ne correspond pas à une couleur de la table logique, le stylet est dessiné avec une couleur dégradée. Le **PS_INSIDEFRAME** style est identique à **PS_SOLID** si la largeur du stylet est inférieur ou égal à 1.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#101;](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="fromhandle"></a>CPen::FromHandle  
 Retourne un pointeur vers un `CPen` objet en fonction d’un handle à un objet de pen Windows GDI.  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>Paramètres  
 *hPen*  
 `HPEN`handle du stylet GDI de Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CPen` objet en cas de réussite ; sinon **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Si aucun objet `CPen` n'est attaché au handle, un objet `CPen` temporaire est créé et attaché. Ce fichier temporaire `CPen` objet est valide uniquement jusqu'à la prochaine fois que l’application dispose de temps d’inactivité dans sa boucle d’événements, alors graphique temporaire de tous les objets sont supprimés. En d’autres termes, l’objet temporaire est valide uniquement pendant le traitement du message de fenêtre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#105;](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="getextlogpen"></a>CPen::GetExtLogPen  
 Obtient un **EXTLOGPEN** structure sous-jacente.  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Paramètres  
 `pLogPen`  
 Pointe vers une [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) structure qui contient des informations sur le stylet.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le **EXTLOGPEN** structure définit le style, la largeur et les attributs de forme d’un stylet. Par exemple, appeler `GetExtLogPen` pour faire correspondre le style particulier d’un stylet.  
  
 Consultez les rubriques suivantes dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur les attributs de stylet :  
  
- [Fonction GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant montre l’appel `GetExtLogPen` pour extraire les attributs d’un stylet, puis créez un nouveau stylet cosmétique avec la même couleur.  
  
 [!code-cpp[NVC_MFCDocView&#102;](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="getlogpen"></a>CPen::GetLogPen  
 Obtient un `LOGPEN` structure sous-jacente.  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Paramètres  
 `pLogPen`  
 Pointe vers une [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) structure destinée à contenir des informations sur le stylet.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le `LOGPEN` structure définit le style, la couleur et le motif d’un stylet.  
  
 Par exemple, appeler `GetLogPen` pour faire correspondre le type particulier de stylet.  
  
 Consultez les rubriques suivantes dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur les attributs de stylet :  
  
- [Fonction GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant montre l’appel `GetLogPen` pour récupérer un caractère du stylet et puis créer un nouveau stylet solid avec la même couleur.  
  
 [!code-cpp[NVC_MFCDocView&#103;](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="operator_hpen"></a>CPen::operator HPEN  
 Obtient le handle Windows GDI attaché de le `CPen` objet.  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si réussie, un handle vers l’objet Windows GDI représenté par le `CPen` objet ; sinon **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur est un opérateur de cast, qui prend en charge l’utilisation directe d’une `HPEN` objet.  
  
 Pour plus d’informations sur l’utilisation des objets graphiques, consultez l’article [les objets de graphique](http://msdn.microsoft.com/library/windows/desktop/dd144962) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#104;](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [CGdiObject (classe)](../../mfc/reference/cgdiobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CBrush (classe)](../../mfc/reference/cbrush-class.md)

