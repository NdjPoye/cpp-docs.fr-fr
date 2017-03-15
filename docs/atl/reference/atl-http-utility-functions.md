---
title: "Fonctions de l’utilitaire HTTP ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
translationtype: Machine Translation
ms.sourcegitcommit: 9ab4b38b2ba14aca2240d12fff966d36750a3229
ms.openlocfilehash: dd8b3a279148e2a5b72d96724c329e49cd5d3e5f
ms.lasthandoff: 02/24/2017

---
# <a name="atl-http-utility-functions"></a>Fonctions de l’utilitaire HTTP ATL

Ces fonctions prennent en charge la manipulation d’URL.

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Canonicalise une URL qui inclut la conversion des espaces et des caractères non sécurisés en séquences d’échappement.|  
|[AtlCombineUrl](#atlcombineurl)|Combine une URL de base et une URL relative en une URL unique et canonique.|  
|[AtlEscapeUrl](#atlescapeurl)|Convertit tous les caractères non sécurisés en séquences d’échappement.|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Obtient le numéro de port par défaut associé à un protocole Internet particulier ou le schéma.|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Détermine si un caractère est utilisé dans une URL.|  
|[AtlUnescapeUrl](#atlunescapeurl)|Convertit les caractères d’échappement vers leurs valeurs d’origine.|  
|[RGBToHtml](#rgbtohtml)|Convertit un [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur texte HTML correspondant à cette valeur de couleur.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Appelez cette fonction pour convertir une heure système en une chaîne au format approprié pour être utilisée dans les en-têtes HTTP.|

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlutil.h  

## <a name="a-nameatlcanonicalizeurla-atlcanonicalizeurl"></a><a name="atlcanonicalizeurl"></a>AtlCanonicalizeUrl
Appelez cette fonction pour rendre canonique une URL, notamment afin de convertir les caractères et espaces non sécurisés en séquences d'échappement.  
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `szUrl`  
 URL à mettre en forme canonique.  
  
 `szCanonicalized`  
 Mémoire tampon allouée par l’appelant de recevoir l’URL au format canonique.  
  
 `pdwMaxLength`  
 Pointeur vers une variable qui contient la longueur en caractères de `szCanonicalized`. Si la fonction réussit, la variable reçoit le nombre de caractères écrits dans la mémoire tampon non compris le caractère null de fin. Si la fonction échoue, la variable reçoit la longueur en octets de la mémoire tampon, y compris l’espace pour le caractère null de fin.  
  
 `dwFlags`  
 Indicateurs de contrôle du comportement de cette fonction. Consultez la page [ATL_URL indicateurs](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** en cas de réussite, **FALSE** en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Se comporte comme la version actuelle de [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) mais ne nécessite ne pas de WinInet ou Internet Explorer soit installé.  
  
### <a name="see-also"></a>Voir aussi  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="a-nameatlcombineurla-atlcombineurl"></a><a name="atlcombineurl"></a>AtlCombineUrl
 Appelez cette fonction pour associer une URL de base et une URL relative en une URL unique et canonique.  
  
```    
inline BOOL AtlCombineUrl(  
   LPCTSTR szBaseUrl,  
   LPCTSTR szRelativeUrl,  
   LPTSTR szBuffer,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 *szBaseUrl*  
 L’URL de base.  
  
 *szRelativeUrl*  
 L’URL par rapport à l’URL de base.  
  
 `szBuffer`  
 Mémoire tampon allouée par l’appelant de recevoir l’URL au format canonique.  
  
 `pdwMaxLength`  
 Pointeur vers une variable qui contient la longueur en caractères de `szBuffer`. Si la fonction réussit, la variable reçoit le nombre de caractères écrits dans la mémoire tampon non compris le caractère null de fin. Si la fonction échoue, la variable reçoit la longueur en octets de la mémoire tampon, y compris l’espace pour le caractère null de fin.  
  
 `dwFlags`  
 Indicateurs de contrôle du comportement de cette fonction. Consultez la page [ATL_URL indicateurs](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** en cas de réussite, **FALSE** en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Se comporte comme la version actuelle de [InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) mais ne nécessite ne pas de WinInet ou Internet Explorer soit installé.  
  
## <a name="a-nameatlescapeurla-atlescapeurl"></a><a name="atlescapeurl"></a>AtlEscapeUrl
 Appelez cette fonction pour convertir tous les caractères non sécurisés en séquences d'échappement.  
  
```    
inline BOOL AtlEscapeUrl(  
   LPCSTR szStringIn,  
   LPSTR szStringOut,  
   DWORD* pdwStrLen,  
   DWORD dwMaxLength,  
   DWORD dwFlags = 0) throw();  
   
inline BOOL AtlEscapeUrl(  
   LPCWSTR szStringIn,  
   LPWSTR szStringOut,  
   DWORD* pdwStrLen,  
   DWORD dwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszStringIn`  
 L’URL à convertir.  
  
 `lpszStringOut`  
 Tampon allouée par l’appelant à laquelle l’adresse URL convertie sera écrit.  
  
 `pdwStrLen`  
 Pointeur vers une variable DWORD. Si la fonction réussit, `pdwStrLen` reçoit le nombre de caractères écrits dans la mémoire tampon, non compris le caractère null de fin. Si la fonction échoue, la variable reçoit la longueur en octets de la mémoire tampon, y compris l’espace pour le caractère null de fin. Lorsque vous utilisez la version à caractères larges de cette méthode, `pdwStrLen` reçoit le nombre de caractères requis, pas le nombre d’octets.  
  
 `dwMaxLength`  
 La taille de la mémoire tampon `lpszStringOut`.  
  
 `dwFlags`  
 Indicateurs de contrôle du comportement de cette fonction. Consultez la page [ATL_URL indicateurs](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** en cas de réussite, **FALSE** en cas d’échec.  
  
## <a name="atlgetdefaulturlport"></a> 
 Appelez cette fonction pour obtenir le numéro de port par défaut associé à un protocole ou un modèle Internet particulier.  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 *m_nScheme*  
 Le [ATL_URL_SCHEME](atl-url-scheme-enum.md) qui permet d’identifier le schéma pour lequel vous souhaitez obtenir le numéro de port.  
  
### <a name="return-value"></a>Valeur de retour  
 Le [ATL_URL_PORT](atl-typedefs.md#atl_url_port) associé au schéma spécifié ou ATL_URL_INVALID_PORT_NUMBER si le schéma n’est pas reconnu.  

## <a name="a-nameatlisunsafeurlchara-atlisunsafeurlchar"></a><a name="atlisunsafeurlchar"></a>AtlIsUnsafeUrlChar
 Appelez cette fonction pour déterminer si un caractère peut être utilisé de manière sécurisée dans une URL.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `chIn`  
 Caractère à tester pour la sécurité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** si le caractère d’entrée est dangereux, **FALSE** dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Les caractères qui ne doivent pas être utilisés dans les URL peut être testés à l’aide de cette fonction et converti à l’aide de [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
## <a name="a-nameatlunescapeurla-atlunescapeurl"></a><a name="atlunescapeurl"></a>AtlUnescapeUrl
 Appelez cette fonction pour convertir les caractères ayant fait l'objet d'une séquence d'échappement vers leurs valeurs d'origine.  
  
```    
inline BOOL AtlUnescapeUrl(  
   LPCSTR szStringIn,  
   LPSTR szStringOut,  
   LPDWORD pdwStrLen,  
   DWORD dwMaxLength) throw();  

inline BOOL AtlUnescapeUrl(  
   LPCWSTR szStringIn,  
   LPWSTR szStringOut,  
   LPDWORD pdwStrLen,  
   DWORD dwMaxLength) throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszStringIn`  
 L’URL à convertir.  
  
 `lpszStringOut`  
 Tampon allouée par l’appelant à laquelle l’adresse URL convertie sera écrit.  
  
 `pdwStrLen`  
 Pointeur vers une variable DWORD. Si la fonction réussit, la variable reçoit le nombre de caractères écrits dans la mémoire tampon non compris le caractère null de fin. Si la fonction échoue, la variable reçoit la longueur en octets de la mémoire tampon, y compris l’espace pour le caractère null de fin.  
  
 `dwMaxLength`  
 La taille de la mémoire tampon `lpszStringOut`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** en cas de réussite, **FALSE** en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Annule le processus de conversion appliqué par [AtlEscapeUrl](#atlescapeurl).  
  
## <a name="a-namergbtohtmla-rgbtohtml"></a><a name="rgbtohtml"></a>RGBToHtml
Convertit un [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur texte HTML correspondant à cette valeur de couleur.  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>Paramètres  
 `color`  
 Une valeur de couleur RVB.  
  
 `pbOut`  
 Mémoire tampon allouée par l’appelant qui recevra le texte pour la valeur de couleur HTML. La mémoire tampon d’espace doit être d’au moins 8 caractères, y compris un espace pour le terminateur null).  
  
 *nBuffer*  
 La taille en octets de la mémoire tampon (y compris l’espace pour le terminateur null).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** en cas de réussite, **FALSE** en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Une valeur de couleur HTML est un signe dièse suivi d’une valeur hexadécimale à 6 chiffres pour chacun des composants rouges, verts et bleus de la couleur à l’aide de 2 chiffres (par exemple, est blanc #FFFFFF).  
  
## <a name="a-namesystemtimetohttpdatea-systemtimetohttpdate"></a><a name="systemtimetohttpdate"></a>SystemTimeToHttpDate
Appelez cette fonction pour convertir une heure système en une chaîne au format approprié pour être utilisée dans les en-têtes HTTP.  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>Paramètres  
 `st`  
 L’heure système doivent être obtenues comme une chaîne de format HTTP.  
  
 *strTime*  
 Une référence à une variable de chaîne pour recevoir le HTTP date heure comme défini dans RFC 2616 ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) et RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts](../../atl/active-template-library-atl-concepts.md)   
 [Composants COM bureau ATL](../../atl/atl-com-desktop-components.md)   


