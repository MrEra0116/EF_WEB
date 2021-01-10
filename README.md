# .NET Project
## 1.Project Introduction
>Our project is dedicated to helping teachers in hebut create an educational administration program(Call this application for short)for them to manage students and classes,and our program is displayed by web interface.
## 2.Project function
>①`The teachers are able to create students and classes in the application and to ass students to
classes.`  
>②`The teachers are able to modify the classes and the students.`  
>③`The teachers are able to delete a student or a class.`  
>④`The teacher are able to add or remove students from classes.`  
## 3.Installation Environment
>①`Install visual studio 2019`,the download address is:https://visualstudio.microsoft.com/zh-hans/vs/  
>②Use the system's own decompression software or third-party decompression software similar to band zip to `unzip the package containing the program we uploaded.`

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/2.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/3.png)

>①`Open EF_ WEB.sln file in vs2019`  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/4.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/5.png) 

## 4.Use steps
### ❌Warning
>`Note that webform1.aspx is used to test and debug all functions, please do not run it, otherwise it will be used to cover the existing database data.`  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/6.png)  

### Function Realization  
#### 4.1 Add and Delete student
>①`Run the 'default.aspx' file`,all the following functions are implemented on the basis of executing this file.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/7.png)  

>②`Enter the name of the added student number and click Add`,and you can see the student is be added.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/8.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/9.png)  

>③`Click Delete`,and you can see the student is be deleted.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/10.png)  

#### 4.2 Update the student
>①`Input the student number of a student in the database, input the corrected name, and click Update`,you can see the student is updated.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/11.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/12.png)  

#### 4.3 Select the student
>①`Enter the student number of a student in the database and click Select`,you can see the selected student.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/13.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/14.png)  

#### 4.4 Add class and Delete class
>①`Enter the name of the added class number and click Add`,and you can see the class is be added.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/15.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/16.png)  

>③`Click Delete`,and you can see the class is be deleted.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/17.png)  

#### 4.5 Update the class
>①`Input the class number of a class in the database, input the corrected name, and click Update`,you can see the class is updated.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/18.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/19.png)  

#### 4.6 Select the class
>①`Enter the class number of a class in the database and click Select`,you can see the selected class.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/20.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/21.png)  

#### 4.7 Add student to the class and Delete student from the class
>①`Input the existing student number and class number in the database and click Add`,and you can see the student is added to the class you input.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/22.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/23.png)  

>②`Click Delete`,and you can see the student is deleted from the class.

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/24.png)  

#### 4.8 Select all information of a student according to the student number
>①`Input the student's number,and click the select`,and you can see all the student's information.

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/25.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/26.png)  

## 5.Program Composition  
### 5.1 Frame Composition  
#### 5.1.1 ControllerLayer  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/27.png)  

BLL.cs  Code:
```using System;
using System.Collections.Generic;
using System.Linq;
using System.Linq.Expressions;
using System.Text;
using System.Threading.Tasks;


namespace WEBEF
{

    public static class BLL<T> where T : class, new()
    {
        private static IDAL<T> dal = new DAL<T>();

        /// <summary>
        /// add
        /// </summary>
        /// <param name="model"></param>
        public static int Add(T model)
        {
            return dal.Add(model);
        }

        /// <summary>
        /// delete
        /// </summary>
        /// <param name="whereLambda"></param>
        public static int Delete(Expression<Func<T, bool>> whereLambda)
        {
            return dal.Delete(whereLambda);
        }

        /// <summary>
        /// update
        /// </summary>
        /// <param name="whereLambda"></param>
        /// <param name="propertyNames"></param>
        /// <param name="perpertyValues"></param>
        /// <returns></returns>
        public static int Update(Expression<Func<T, bool>> whereLambda, string[] propertyNames, object[] perpertyValues)
        {
            return dal.Update(whereLambda, propertyNames, perpertyValues);
        }

        /// <summary>
        /// select
        /// </summary>
        /// <param name="whereLambda"></param>
        /// <returns></returns>
        public static List<T> GetModelList(Expression<Func<T, bool>> whereLambda)
        {
            return dal.GetModelList(whereLambda);
        }
    }
}
```
#### 5.1.2 ModelLayer  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/28.png)  

dbModel1.cs Code:
```

    using System;
    using System.Data.Entity;
    using System.ComponentModel.DataAnnotations.Schema;
    using System.Linq;
namespace WEBEF
{
    public partial class dbModel1 : DbContext
    {
        public dbModel1()
            : base("name=dbModel1")
        {
        }

        public virtual DbSet<Classes> Classes { get; set; }
        public virtual DbSet<Student> Student { get; set; }
        public virtual DbSet<Study> Study { get; set; }

        protected override void OnModelCreating(DbModelBuilder modelBuilder)
        {
            modelBuilder.Entity<Student>()
                .HasOptional(e => e.Study)
                .WithRequired(e => e.Student)
                .WillCascadeOnDelete();
        }
    }
}
```

Student.cs  Code:
``` using System;
    using System.Collections.Generic;
    using System.ComponentModel.DataAnnotations;
    using System.ComponentModel.DataAnnotations.Schema;
    using System.Data.Entity.Spatial;
namespace WEBEF
{
    [Table("Student")]
    public partial class Student
    {
        [Key]
        [DatabaseGenerated(DatabaseGeneratedOption.None)]
        public int Sno { get; set; }

        [Required]
        [StringLength(50)]
        public string Name { get; set; }

        public virtual Study Study { get; set; }
    }
}
```

Classes.cs  Code:
``` using System;
    using System.Collections.Generic;
    using System.ComponentModel.DataAnnotations;
    using System.ComponentModel.DataAnnotations.Schema;
    using System.Data.Entity.Spatial;
namespace WEBEF
{
    public partial class Classes
    {
        [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Usage", "CA2214:DoNotCallOverridableMethodsInConstructors")]
        public Classes()
        {
            Study = new HashSet<Study>();
        }

        [Key]
        [DatabaseGenerated(DatabaseGeneratedOption.None)]
        public int Cno { get; set; }

        [Required]
        [StringLength(50)]
        public string CName { get; set; }

        [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Usage", "CA2227:CollectionPropertiesShouldBeReadOnly")]
        public virtual ICollection<Study> Study { get; set; }
    }
}
```

Study.cs  Code:
``` using System;
    using System.Collections.Generic;
    using System.ComponentModel.DataAnnotations;
    using System.ComponentModel.DataAnnotations.Schema;
    using System.Data.Entity.Spatial;
namespace WEBEF
{
    [Table("Study")]
    public partial class Study
    {
        public int Cno { get; set; }

        [Key]
        [DatabaseGenerated(DatabaseGeneratedOption.None)]
        public int Sno { get; set; }


        public virtual Classes Classes { get; set; }

        public virtual Student Student { get; set; }
    }
}
```
#### 5.1.3 DataAccess  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/29.png)  

DAL.cs  Code:
```using System;
using System.Collections.Generic;
using System.Linq;
using System.Linq.Expressions;
using System.Reflection;
using System.Text;
using System.Threading.Tasks;
namespace WEBEF
{
    public class DBServices
    {

        public static dbModel1 db = new dbModel1();
    }
    public class DAL<T> :  IDAL<T> where T : class, new()
    {
        /// <summary>
        /// 增
        /// </summary>
        /// <param name="model"></param>
        /// <returns></returns>
        public int Add(T model)
        {
            DBServices.db.Set<T>().Add(model);
            return DBServices.db.SaveChanges();
        }

        /// <summary>
        /// 删
        /// </summary>
        /// <param name="whereLambda"></param>
        /// <returns></returns>
        public int Delete(Expression<Func<T, bool>> whereLambda)
        {
            
                var dbQuery =DBServices.db.Set<T>();

                //先查询 对应表的 集合
                var list = dbQuery.Where(whereLambda).ToList();

                //遍历集合 里要删除的元素
                foreach (var item in list)
                {
                    //标记为 删除状态
                    dbQuery.Remove(item);
                }
                return DBServices.db.SaveChanges();
            
        }

        /// <summary>
        /// 改
        /// </summary>
        /// <param name="whereLambda"></param>
        /// <param name="propertyNames"></param>
        /// <param name="perpertyValues"></param>
        /// <returns></returns>
        public int Update(Expression<Func<T, bool>> whereLambda, string[] propertyNames, object[] perpertyValues)
        {
          

                //1、查询要修改的对象集合
                var list =DBServices.db.Set<T>().Where<T>(whereLambda).ToList();

                //2、获取要修改的对象的类型
                Type t = typeof(T);

                //3、循环要修改的实体对象，并根据要修改的属性名修改对象对应的属性值
                foreach (var item in list)
                {
                    //循环 要修改的属性 名称， 并 反射取出 t 中的 属性对象
                    for (int index = 0; index < propertyNames.Length; index++)
                    {
                        //获取要修改的属性名
                        string pName = propertyNames[index];

                        //获取属性对象
                        PropertyInfo pi = t.GetProperty(pName);

                        //调用属性对象的 SetValue方法 为当前循环的 item对象 对应的属性赋值
                        pi.SetValue(item, perpertyValues[index], null);
                    }
                }
                return DBServices.db.SaveChanges();
            
        }

        /// <summary>
        /// 查
        /// </summary>
        /// <param name="whereLambda"></param>
        /// <returns></returns>
        public List<T> GetModelList(Expression<Func<T, bool>> whereLambda)
        {
          
                return DBServices.db.Set<T>().Where(whereLambda).ToList();
            
        }
    }
}
```

IDAL.cs  Code:
```using System;
using System.Collections.Generic;
using System.Linq;
using System.Linq.Expressions;
using System.Text;
using System.Threading.Tasks;

namespace WEBEF
{
    public interface IDAL<T> where T : class, new()
    {
        /// <summary>
        /// 增
        /// </summary>
        /// <param name="model"></param>
        /// <returns></returns>
        int Add(T model);

        /// <summary>
        /// 删
        /// </summary>
        /// <param name="whereLambda"></param>
        /// <returns></returns>
        int Delete(Expression<Func<T, bool>> whereLambda);

        /// <summary>
        /// 改
        /// </summary>
        /// <param name="whereLambda"></param>
        /// <param name="propertyNames"></param>
        /// <param name="perpertyValues"></param>
        /// <returns></returns>
        int Update(Expression<Func<T, bool>> whereLambda, string[] propertyNames, object[] perpertyValues);

        /// <summary>
        /// 查
        /// </summary>
        /// <param name="whereLambda"></param>
        /// <returns></returns>
        List<T> GetModelList(Expression<Func<T, bool>> whereLambda);
    }
}
```
#### 5.2 Database Framework  
>`Entity Framework`

### 6.Our team
>KANG Xingkai
>LIU Jiyuan
>ZUO Yilin
>ZHOU Yuxuan
>CHENG Ruoyi
