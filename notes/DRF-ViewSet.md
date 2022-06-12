---
type : knowledges
detail : 
content_type :
---

[[Python]]
created : 2022-06-05 15:49
tags : #🖥️Note/Python  #🖥️Note/Django 

# DRF-ViewSet
- ViesSets
	- DRF에서 비슷한 연관된 view 클래스를 하나의 클래스로 구현 한 것
	- 다른 프레임워크에서 Resources 또는 Controllers라고 부르기도 함
- class-based view의 한 종류로,메소드 핸들러를 제공하지 않음
	- `.get()`, `.post()` 대신 `.list()`, `.create()`를 제공
	- `.as_view()`를 통하여 지정할 수 있음
	- url 설정 내에서 ViewSet의 각 view를 명시적으로 등록하는 것 보다, router 클래스로 등록하는 것이 좋음
- `APIView` 클래스를 상속받아 제작되어, 기본적인 작동방식은 APIView에서 확장된 형식
	- attribute로 다음을 가짐
		- renderer_classes, parser_classes, authentication_classes, throttle_classes, permission_classes, content_negotiation_class
	- 추가적인 장점으로 queryset을 지정하여 여러 view의 유사한 로직을 묶을 수 있고, 라우터를 지정할 때 URL conf를 신경 쓸 필요 없음 
- 추가적인 라우터를 사용할 때, `@action`데코레이터를 활용할 수 있음
	- `@action`데코레이터에서 detail=True를 통하여 

## ViewSet 작성 방법
```python
class UserViewSet(ViewSet):
    authentication_classes = []
    serializer_class = SampleSerializer
    queryset = Sample.objects.all()
```
- 일반적으로 app 이름, 모델 이름 + ViewSet으로 클래스 이름을 지정하고 ViewSet을 상속받아 생성
- 기본적으로 authentication_classes, serializer_class, queryset을 선언하는 것이 좋음

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
- 기본적인 CRUD 함수의 method 핸들러는 다음과 같이 주어짐

# 참조
- [DRF ViewSets](https://www.django-rest-framework.org/api-guide/viewsets/)
- [DRF views - 코드와 도식화로 잘 설명된 클](https://sss20-02.tistory.com/66)
