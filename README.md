1. Tạo codeCommit 
    - https://docs.aws.amazon.com/codepipeline/latest/userguide/samples/SampleApp_Linux.zip
2. Tạo role cho ecs có quyền try cập vào s3 -> tại vì các code mà deploy lên nó sẽ được nhảy vào s3 nên là phải cho phép cái server mình try cập vào cái s3 này
3. Tạo role codedeploy
4. Cài ec2 để deploy code
    #!/bin/bash
    - yum -y update
    - yum install -y ruby
    - yum install -y aws-cli
    - cd /home/ec2-user
    - aws s3 cp s3://aws-codedeploy-us-east-2/latest/install . --region us-east-2
    - chmod +x ./install
    - ./install auto
5. Tạo codedeploy
    - EC2/On-premises -> cho mt ec2
    - AWS Lamda -> cho mt serverless
    - Amazon EC2 -> chạy cho mt sử dụng với docker

    * note khi tạo group (Create deployment group)
        - Đặt name cho instance (bắt buộc),
        - 
6. Tạo codePipeline
    -  ở bước tạo CodePipeline khi Add source stage thì thay vì chọn AWS CodeCommit thì chọn Githup
    * note : Ở bước Build - optional (vì mình đã có script trong chính thư mục code rồi nên k cần phải chọn AWS codebuild or Jenkins nữa)
7. Test deploy tự động