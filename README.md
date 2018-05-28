### Các mã lệnh khởi tạo
- Cài đặt Angular CLI: npm install -g @angular/cli
- Khởi tạo 1 project mới: ng new "new project's name"
- Build ứng dụng: ng serve --open (The --open flag opens a browser to http://localhost:4200/)
- Khởi tạo 1 component mới: ng generate component "new component's name"
- Khởi tạo 1 service mới: ng generate service "new service's name"
### Component
- Gồm 3 file cơ bản:
  - app.component.css: the component's private CSS styles.
  - app.component.html: the component template, viết bằng HTML.
  - app.component.ts: the component class code, viết bằng TypeScript.
    - Luôn luôn import class Component từ thư viện của Angular và chú thích nó bằng @Component
    - @Component khởi tạo gồm 3 thành phần metadata:
      - Selector:  the component's CSS element selector
      - TemplateUrl: the location of the component's template file.
      - StyleUrls: the location of the component's private CSS styles.
- Tạo các liên kết dữ liệu bằng directive NgModel, tạo vòng lặp dữ liệu vs NgFor, kiểm tra điều kiện với NgIf (để sử dụng các directive Ng- cần import class FormsModule)
- AppModule: quản lý các class thư viện
  - Declaration: khai báo các component sử dụng
  - Import: khai báo các class
### Service
- @Injectable service
  - Được import ngay khi khởi tạo service mới và được khai báo dạng @Injectable, là một thành phần của 1 hệ thống phụ thuộc injection. Các lớp cung cấp 1 injection service, và bản thân nó cũng có thể có injection phụ thuộc.
  - @Injectable() khai báo các metadata cho service, giống như component
  - Inject a service: constructor(private/public service's name: service's type)
- NgOnInIt
  - Gọi sau khi các thuộc tính của 1 directive được khởi tạo
  - No parameters, return void
- Observable Data
  - subcribe()
- Service-in-service: có thể inject 1 service trong 1 service khác
### Routing
- Routes: dùng để hiển thị khi người dùng click vào link hay đường dẫn URL trên thanh trình duyệt. Gồm 2 thành phần chính:
  - path: 1 string dùng để đối chiếu với URL trên thanh trình duyệt
  - component: component router tạo ra khi navigating đến router đó
- Thêm AppRoutingModule: ng generate module app-routing --flat --module=app
- Thêm routes: type Routes = Route[ ];
- RouterModule.ForRoot()
- Thêm routerOutlet vào app.component.html
- RouterLink: 
### HTTP
- Install the In-memory Web API package from npm: npm install angular-in-memory-web-api --save
- Http methods return one value:
  - All HttpClient methods return an RxJS Observable of something.
  - HTTP is a request/response protocol. You make a request, it returns a single response.
- HttpClient.get returns response data:
- Error handling: import { catchError, map, tap } from 'rxjs/operators';
- Tap into the Observable
