발표자 : 정준 대리


심댈 코멘트 :

Java와 .NET 두 기술이 서로 달라보인다면, 두 기술의 기술적 차이보다는 양 진영의 철학의 차이와 그에 따른 접근방식의 차이가 아닐까 합니다.

틀릴 각오를 하고 쉽게 비유하자면, 자바 진영이 DIY(Do It Yourself)라면, MS진영은 Out of BOX에 비유하고 싶습니다. 자바진영의 기술들은 오픈되어있고 사용하려면 설치, 세팅하는데 시간이 듭니다. 반면, MS는 설치하면 바로 사용이 가능한 것처럼 보입니다. 윈도우즈나 IIS나 Visual Studio 처럼요.

하지만, 이 두 차이는 조금만 깊이 들어가면 비슷해져 버립니다. C#과 Java의 관계라든가, J2EE Container(웹로직, 웹스피어 등)와 IIS의 관계 그리고 JVM과 CLR의 관계처럼 같은 문제를 풀기위한 서로 다른 방법이기 때문에, 해결방법도 서로를 닮아있고 또 영향을 주고 받는 것 같습니다.

다만, 시스템 운영자로서 감안해야할 점이 있다면, 우리가 시스템을 개발단계에서부터 개입할 수 있는 것이 아니라, 이미 개발된 그리고 일정기간 운영되어온 시스템을 다룬다는 점입니다. MS 닷넷에 CI(Continuous Integration)툴`*`이 없는 것은 아니지만, 이미 설치/세팅되어 사용되어지고 있지 않다면 운영단에 도입하는 일은 만만치 않습니다.

`*` 닷넷에는 CruiseControl.net 이 있습니다. http://www.cruisecontrolnet.org/