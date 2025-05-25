# **Django Product Catalog with Category Management**

## **Project Overview**

This project is a comprehensive **Django-based web application** that provides a robust system for managing **product categories** and their associated **products**. It is designed to help businesses, especially in retail or e-commerce, organize and showcase their inventory effectively.

The application features a clean architecture with **well-defined models**, **CRUD functionality**, **searching**, and **filtering** capabilities. It also incorporates image uploads for categories, improving the visual appeal and user experience.

---

## **Key Features and Theory**

### **1. Data Modeling and Relationships**

- The project uses Django's **ORM (Object Relational Mapping)** to define two main models:
  - **Category**: Represents a product category with fields such as `name`, `description`, and an **image** using `ImageField`.
  - **Product**: Represents individual products linked to categories via a **ForeignKey relationship**. This relationship is crucial for organizing products hierarchically and enables querying products by category efficiently.

- The **ForeignKey with `related_name='products'`** allows reverse lookup, meaning from a category instance, you can easily access all its products (`category.products.all()`).

### **2. CRUD Operations**

- **Create, Read, Update, Delete (CRUD)** are implemented for both models. This enables full lifecycle management of products and categories.
- CRUD is typically handled via:
  - **Forms** for input validation and user interaction.
  - **Class-based views or function-based views** for handling the HTTP methods.
  - **Templates** to render data and forms on the frontend.

- This layered approach follows the **MVC (Model-View-Controller)** architectural pattern, improving maintainability and scalability.

### **3. Image Handling in Django**

- The **ImageField** in the Category model facilitates image uploads.
- Images are stored on the filesystem (in a `media/` directory), and Django serves them during development via settings:
  - `MEDIA_URL`: The URL prefix to access media files.
  - `MEDIA_ROOT`: The file system path where uploaded files are stored.
- Handling image uploads improves the **user interface** by providing visual context to categories.

### **4. Filtering and Searching**

- Products can be filtered by:
  - **Category**: Display only products belonging to a selected category.
  - **Active Status**: Show only active products (`is_active=True`), hiding discontinued or inactive items.
  - **Tag**: Filter products by dietary tags like vegetarian/non-vegetarian.

- **Search functionality** allows users to find products by their **name**, improving navigation and discoverability.

### **5. Scalability and Extensibility**

- The project’s modular design allows easy addition of features such as:
  - **Product images and galleries**.
  - **Pagination** for large product lists.
  - **AJAX-powered live search** and filtering.
  - **REST API endpoints** for mobile apps or third-party integrations.
  - **User authentication and role-based permissions** for admin and staff.

---

## **Technology Stack**

- **Backend:** Django (Python web framework) for rapid development and clean design.
- **Database:** SQLite for development; easily replaceable with PostgreSQL, MySQL, etc.
- **Frontend:** Django Templates with HTML and CSS.
- **Media Handling:** Django’s built-in media serving combined with Pillow library for image processing.
- **Version Control:** Git (recommend setting up `.gitignore` to exclude `media/` and `db.sqlite3`).

---

## **Setup and Installation**

1. **Clone the repo:**

```bash
git clone https://github.com/yourusername/django-product-catalog.git
cd django-product-catalog
