---
title: ATL HTTP 效用函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36b0647863076661eb130da1cde694b128f49d47
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026083"
---
# <a name="atl-http-utility-functions"></a>ATL HTTP 效用函数

这些函数支持的 Url 的操作。

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Canonicalizes URL，其中包含不安全字符和空格转换为转义序列。|  
|[AtlCombineUrl](#atlcombineurl)|将基 URL 和相对 URL 合并到单个的规范 URL。|  
|[AtlEscapeUrl](#atlescapeurl)|将所有不安全字符转义序列的转换。|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|获取与特定 Internet 协议或方案关联的默认端口号。|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|确定字符是否在 URL 中安全使用。|  
|[AtlUnescapeUrl](#atlunescapeurl)|转义字符转换回其原始值。|  
|[RGBToHtml](#rgbtohtml)|将转换[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)该颜色值对应的 HTML 文本的值。|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|调用此函数可将系统时间转换为采用适合在 HTTP 标头中使用的格式的字符串。|

## <a name="requirements"></a>要求  
 **标头：** atlutil.h  

## <a name="atlcanonicalizeurl"></a> AtlCanonicalizeUrl
调用此函数可对 URL 进行规范化，包括将不安全的字符和空格转换为转义序列。  
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>参数  
 *szUrl*  
 要规范化的 URL。  
  
 *szCanonicalized*  
 若要接收的规范化的 URL 的调用方分配的缓冲区。  
  
 *pdwMaxLength*  
 指向包含的字符长度的变量*szCanonicalized*。 如果函数成功，该变量接收到包括终止 null 字符的缓冲区写入的字符数。 如果函数失败，该变量接收所需的长度以字节为单位的缓冲区包括终止 null 字符的空间。  
  
 *dwFlags*  
 ATL_URL 标志控制此函数的行为。 

- ATL_URL_BROWSER_MODE 不会进行编码或解码字符后"#"或"？"，并不会删除尾随空格后"？"。 如果未指定此值，编码整个 URL，并删除尾随空格。
- ATL_URL_DECODE 将所有 %xx 序列都转换为字符，其中包括转义序列之前分析该 URL。
- ATL_URL_ENCODE_PERCENT 进行编码时遇到任何百分比符号的组合。 默认情况下，不进行编码百分号。
- ATL_URL_ENCODE_SPACES_ONLY 进行编码的共享空间。
- ATL_URL_ESCAPE 转换所有到其对应的字符转义序列 （%xx)。
- ATL_URL_NO_ENCODE 不转换不安全字符进行转义序列。
- ATL_URL_NO_META 不会删除元序列 (如"。"和"..") 从该 URL。 
  
### <a name="return-value"></a>返回值  
 如果成功，则返回 TRUE FALSE 失败。  
  
### <a name="remarks"></a>备注  
 行为类似于最新版[InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) ，但不需要 WinInet 或 Internet Explorer 安装。  
  
### <a name="see-also"></a>请参阅  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="atlcombineurl"></a> AtlCombineUrl
 调用此函数可将基 URL 和相对 URL 合并为单个规范 URL。  
  
```    
inline BOOL AtlCombineUrl(  
   LPCTSTR szBaseUrl,  
   LPCTSTR szRelativeUrl,  
   LPTSTR szBuffer,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>参数  
 *szBaseUrl*  
 基 URL。  
  
 *szRelativeUrl*  
 相对于基 URL URL。  
  
 *szBuffer*  
 若要接收的规范化的 URL 的调用方分配的缓冲区。  
  
 *pdwMaxLength*  
 指向包含的字符长度的变量*szBuffer*。 如果函数成功，该变量接收到包括终止 null 字符的缓冲区写入的字符数。 如果函数失败，该变量接收所需的长度以字节为单位的缓冲区包括终止 null 字符的空间。  
  
 *dwFlags*  
 控制此函数的行为的标志。 请参阅[AtlCanonicalizeUrl](#atlcanonicalizeurl)。  
  
### <a name="return-value"></a>返回值  
 如果成功，则返回 TRUE FALSE 失败。  
  
### <a name="remarks"></a>备注  
 行为类似于最新版[InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) ，但不需要 WinInet 或 Internet Explorer 安装。  
  
## <a name="atlescapeurl"></a> AtlEscapeUrl
 调用此函数可将所有不安全字符转换为转义序列。  
  
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
  
### <a name="parameters"></a>参数  
 *lpszStringIn*  
 要转换的 URL。  
  
 *lpszStringOut*  
 调用方分配的缓冲区将写入转换后的 URL。  
  
 *pdwStrLen*  
 指向一个 DWORD 变量的指针。 如果函数成功， *pdwStrLen*接收到包括终止 null 字符的缓冲区写入的字符数。 如果函数失败，该变量接收所需的长度以字节为单位的缓冲区包括终止 null 字符的空间。 使用此方法的宽字符版本时*pdwStrLen*接收所需的字符，不是数字的字节数。  
  
 *dwMaxLength*  
 缓冲区的大小*lpszStringOut*。  
  
 *dwFlags*  
 ATL_URL 标志控制此函数的行为。 请参阅[ATLCanonicalizeUrl](#atlcanonicalizeurl)有关可能的值。  
  
### <a name="return-value"></a>返回值  
 如果成功，则返回 TRUE FALSE 失败。  
  
## <a name="atlgetdefaulturlport"></a> AtlGetDefaultUrlPort
 调用此函数可获取与特定 Internet 协议或方案关联的默认端口号。  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>参数  
 *m_nScheme*  
 [ATL_URL_SCHEME](atl-url-scheme-enum.md)标识你想要获取的端口号的方案值。  
  
### <a name="return-value"></a>返回值  
 [ATL_URL_PORT](atl-typedefs.md#atl_url_port)如果方案无法识别指定的方案或 ATL_URL_INVALID_PORT_NUMBER 与相关联。  

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar
 调用此函数可了解字符在 URL 中能否安全使用。  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>参数  
 *下巴*  
 要进行测试以确保安全的字符。  
  
### <a name="return-value"></a>返回值  
 如果输入的字符是不安全，则返回 FALSE 否则，则返回 TRUE。  
  
### <a name="remarks"></a>备注  
 不应在 Url 中使用的字符可以使用此函数进行测试和使用转换[AtlCanonicalizeUrl](#atlcanonicalizeurl)。  
  
## <a name="atlunescapeurl"></a> AtlUnescapeUrl
 调用此函数可将转义字符转换为其原始值。  
  
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
  
### <a name="parameters"></a>参数  
 *lpszStringIn*  
 要转换的 URL。  
  
 *lpszStringOut*  
 调用方分配的缓冲区将写入转换后的 URL。  
  
 *pdwStrLen*  
 指向一个 DWORD 变量的指针。 如果函数成功，该变量接收到包括终止 null 字符的缓冲区写入的字符数。 如果函数失败，该变量接收所需的长度以字节为单位的缓冲区包括终止 null 字符的空间。  
  
 *dwMaxLength*  
 缓冲区的大小*lpszStringOut*。  
  
### <a name="return-value"></a>返回值  
 如果成功，则返回 TRUE FALSE 失败。  
  
### <a name="remarks"></a>备注  
 反转转换过程由应用[AtlEscapeUrl](#atlescapeurl)。  
  
## <a name="rgbtohtml"></a> RGBToHtml
将转换[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)该颜色值对应的 HTML 文本的值。  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>参数  
 *颜色*  
 RGB 颜色值。  
  
 *pbOut*  
 若要接收的 HTML 颜色值的文本的调用方分配的缓冲区。 缓冲区必须至少为 8 个字符，包括 null 终止符的占用空间的空间）。  
  
 *nBuffer*  
 以字节为单位 （包括 null 终止符的占用空间） 的缓冲区的大小。  
  
### <a name="return-value"></a>返回值  
 如果成功，则返回 TRUE FALSE 失败。  
  
### <a name="remarks"></a>备注  
 一个 HTML 颜色值是为每个颜色的红色、 绿色和蓝色组件使用的 2 位数的 6 位十六进制值后跟井号 （例如，#FFFFFF 为白色）。  
  
## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate
调用此函数可将系统时间转换为采用适合在 HTTP 标头中使用的格式的字符串。  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>参数  
 *st*  
 若要为 HTTP 格式字符串获取系统时间。  
  
 *strTime*  
 对字符串变量，以接收 HTTP RFC 2616 中定义的日期时间的引用 ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) 和 RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt))。  
  
## <a name="see-also"></a>请参阅  
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM 桌面组件](../../atl/atl-com-desktop-components.md)   

