---
type : knowledges
detail : 
content_type :
---

[[Python]]
created : 2022-06-05 15:49
tags : #๐ฅ๏ธ/โจ๏ธ  #๐ฅ๏ธ/Django 

# DRF-ViewSet
- ViesSets
	- DRF์์ ๋น์ทํ ์ฐ๊ด๋ view ํด๋์ค๋ฅผ ํ๋์ ํด๋์ค๋ก ๊ตฌํ ํ ๊ฒ
	- ๋ค๋ฅธ ํ๋ ์์ํฌ์์ Resources ๋๋ Controllers๋ผ๊ณ  ๋ถ๋ฅด๊ธฐ๋ ํจ
- class-based view์ ํ ์ข๋ฅ๋ก,๋ฉ์๋ ํธ๋ค๋ฌ๋ฅผ ์ ๊ณตํ์ง ์์
	- `.get()`, `.post()` ๋์  `.list()`, `.create()`๋ฅผ ์ ๊ณต
	- `.as_view()`๋ฅผ ํตํ์ฌ ์ง์ ํ  ์ ์์
	- url ์ค์  ๋ด์์ ViewSet์ ๊ฐ view๋ฅผ ๋ช์์ ์ผ๋ก ๋ฑ๋กํ๋ ๊ฒ ๋ณด๋ค, router ํด๋์ค๋ก ๋ฑ๋กํ๋ ๊ฒ์ด ์ข์
- `APIView` ํด๋์ค๋ฅผ ์์๋ฐ์ ์ ์๋์ด, ๊ธฐ๋ณธ์ ์ธ ์๋๋ฐฉ์์ APIView์์ ํ์ฅ๋ ํ์
	- attribute๋ก ๋ค์์ ๊ฐ์ง
		- renderer_classes, parser_classes, authentication_classes, throttle_classes, permission_classes, content_negotiation_class
	- ์ถ๊ฐ์ ์ธ ์ฅ์ ์ผ๋ก queryset์ ์ง์ ํ์ฌ ์ฌ๋ฌ view์ ์ ์ฌํ ๋ก์ง์ ๋ฌถ์ ์ ์๊ณ , ๋ผ์ฐํฐ๋ฅผ ์ง์ ํ  ๋ URL conf๋ฅผ ์ ๊ฒฝ ์ธ ํ์ ์์ 
- ์ถ๊ฐ์ ์ธ ๋ผ์ฐํฐ๋ฅผ ์ฌ์ฉํ  ๋, `@action`๋ฐ์ฝ๋ ์ดํฐ๋ฅผ ํ์ฉํ  ์ ์์
	- `@action`๋ฐ์ฝ๋ ์ดํฐ์์ detail=True๋ฅผ ํตํ์ฌ 

## ViewSet ์์ฑ ๋ฐฉ๋ฒ
```python
class UserViewSet(ViewSet):
    authentication_classes = []
    serializer_class = SampleSerializer
    queryset = Sample.objects.all()
```
- ์ผ๋ฐ์ ์ผ๋ก app ์ด๋ฆ, ๋ชจ๋ธ ์ด๋ฆ + ViewSet์ผ๋ก ํด๋์ค ์ด๋ฆ์ ์ง์ ํ๊ณ  ViewSet์ ์์๋ฐ์ ์์ฑ
- ๊ธฐ๋ณธ์ ์ผ๋ก authentication_classes, serializer_class, queryset์ ์ ์ธํ๋ ๊ฒ์ด ์ข์

```Python
class UserViewSet(viewsets.ViewSet):
    def list(self, request):
        pass

    def create(self, request):
        pass

    def retrieve(self, request, pk=None):
        pass

    def update(self, request, pk=None):
        pass

    def partial_update(self, request, pk=None):
        pass

    def destroy(self, request, pk=None):
        pass
```
- ๊ธฐ๋ณธ์ ์ธ CRUD ํจ์์ method ํธ๋ค๋ฌ๋ ๋ค์๊ณผ ๊ฐ์ด ์ฃผ์ด์ง

# ์ฐธ์กฐ
- [DRF ViewSets](https://www.django-rest-framework.org/api-guide/viewsets/)
- [DRF views - ์ฝ๋์ ๋์ํ๋ก ์ ์ค๋ช๋ ํด](https://sss20-02.tistory.com/66)
