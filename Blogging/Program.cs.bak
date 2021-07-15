using System;
using System.Linq;

namespace Blogging
{
    /// <summary>
    /// https://docs.microsoft.com/en-us/ef/ef6/modeling/code-first/workflows/new-database
    /// </summary>
    internal class Program
    {
        private static void Main(string[] args)
        {
            using (BloggingContext db = new BloggingContext())
            {
                // Create and save a new Blog
                Console.Write("Enter a name for a new Blog: ");
                string name = Console.ReadLine();

                Blog blog = new Blog { Name = name };
                db.Blogs.Add(blog);
                db.SaveChanges();

                // Display all Blogs from the database
                IOrderedQueryable<Blog> query = from b in db.Blogs
                            orderby b.Name
                            select b;

                Console.WriteLine("All blogs in the database:");
                foreach (Blog item in query)
                {
                    Console.WriteLine(item.Name);
                }

                Console.WriteLine("Press any key to exit...");
                Console.ReadKey();
            }
        }
    }
}
