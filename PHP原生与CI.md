原生代码 
```
确保开启
1、
xampp--Apache MySQL
Navicate Sublime

2、
原生PHP连接MYSQL（3306）
 打开数据库连接 mysqli_connect
 选择数据库
 操作表
 
【php支持MYSQL/MYSQLI】
【MYSQL语言tsql】
 
database -> table ->列名（类型、大小、主外键）
    一个主键(自增长,not null非空)、多个外键
    （table1、table2  主外键关联）
    
（1）类型：int char varchar text date timestamp blob
    title varchar(8)[内容多少长度多少，最多8]  
          char(8)[固定8个，不管内容多少]
          【知道长度的时候，用char】
    int：null+1 != 1
    
（2）约束：主键约束 外键约束 非空约束not null                         默认值约束default
```

数据库操作
```
增
  insert into 表名(列名,列名...) values(值,值...)
删
  delete from 表名
  delete from 表名 where 条件
改
  update 表名 set 列名=值,列名=值 where 条件
查
  select * from 表名
  select * from 表名 where 条件(可用逻辑运算符)
//返回结果集(空结果集/多行、一行)
//result()返回多行
//row()返回一行

```

ci
```
application -> controllers -> 首字母大写.php
```
CI配置
```
(1).htaccess放到根目录下
(2)config/autoload.php url/database/session
   config/config.php--evcryption_key
(3)config/databaser.php
```
```
user(uid,uname,pass,flag,header)
blog(bid,title,content,ntime,hits,uid)
```
切内容
```
    iconv_substr(内容,从第几个开始,切几个)......;
```
切割
```
//uri->segment
//segment(1)  -> 控制器名c
//segment(2)  -> 方法名f
$this->uri->segment(第几段);
```
接数据
```
get   $this->input->get();
post  $this->input->post();
delete
input
```

view<=>controllers
```
发送
Get: 1.form get
     2.a标签
     3.$.get
     4.curl get

POST:1.form
     2.$.post
     3.curl post
     4.restful user/login/1
接收
Get: 1.$_GET 
     2.$this->input->get()
     3.$this->uri->segment()
     
POST:1.$_POST
     2.$this->input->post()
     
     

$this->load->view('模板',$data);
$this->load->vars('变量名');
```

controllers<=>models
```
$this->load->model('model名');
$this->model名->方法();

①
$sql='sql拼接';
$query=$this->db->query();
query builder
    return $query;
    return $query->row();
    return $query->result();
    
②
插入
$data=array(
    'account' => $username;
);
$query=$this->db->insert('表名',$data);
return $query;

查询
$data=array(
    'account' => $username;
);
$query=$this->db->get_where('表名',$data);
return $query;
```

相对定位
```
<base href="<?php echo site_url();?>">
```

重点**
```
defined('BASEPATH') OR exit('No direct script access allowed');
class Welcome extends CI_Controller {
	public function __constructor(){
		parent::__construct();
	}
```

获取session数据
```
设置数据
$newdata = array(
    'uid'  =>$rs->USER_ID,
    'name'=>$rs->NAME,
    'logged_in'=>TRUE
);
$this->session->set_userdata($newdata);
获取数据
$this->session->userdata('name');
```
验证码
```
$this->load->helper('captcha');
    1.随机字母或数字
    2.将随机字母或数字放到图片上
    3.图片加噪点
    4.随机字母或数字session通到ajax验证

$vals = array(
    'word'      => rand(1000,9999) ,
    'img_path'  => './captcha/', //存放地址
    'img_url'   => base_url.'captcha/',
    //字体'font_path' => './path/to/fonts/texb.ttf',
    'img_width' => '150',
    'img_height'    => 30,
    'expiration'    => 7200,//图片生存时间
    'word_length'   => 8,
    'font_size' => 16,
    'img_id'    => 'Imageid',
    'pool'      => '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ',

    'colors'    => array(
        'background' => array(255, 255, 255),
        'border' => array(255, 255, 255),
        'text' => array(0, 0, 0),
        'grid' => array(255, 40, 40)
    )
);

$cap = create_captcha($vals);
echo $cap['image'];
```
