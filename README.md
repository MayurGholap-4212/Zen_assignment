# **Django Product Catalog with Category Management**

## **Project Overview**

This Django web application is designed to manage a product catalog efficiently by organizing products into various categories. It provides a complete CRUD (Create, Read, Update, Delete) interface for both Categories and Products, allowing users to add new categories, upload images to visually represent them, and maintain a comprehensive product list.

The application supports advanced features such as searching products by name, filtering based on product status (active/inactive), and categorizing products as vegetarian or non-vegetarian using tags. This makes the platform scalable and user-friendly, ideal for small to medium e-commerce stores or inventory management systems.

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


---

## **Setup and Installation**

1. **Clone the repo:**

    ```bash
    git clone https://github.com/yourusername/django-product-catalog.git
    cd django-product-catalog
    ```

2. **Create virtual environment and activate:**

    ```bash
    python -m venv env
    source env/bin/activate  # Windows: env\Scripts\activate
    ```

3. **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Configure media settings in `settings.py`:**

    ```python
    MEDIA_URL = '/media/'
    MEDIA_ROOT = BASE_DIR / 'media'
    ```

5. **Apply database migrations:**

    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```

6. **Create a superuser (optional):**

    ```bash
    python manage.py createsuperuser
    ```

7. **Run the server:**

    ```bash
    python manage.py runserver
    ```

8. Visit `http://127.0.0.1:8000/` to access the application.

---

## **Folder Structure**

```bash
project_root/
│
├── your_app/
│ ├── models.py # Database models for Category and Product
│ ├── views.py # CRUD and business logic
│ ├── forms.py # Forms for data validation and input
│ ├── urls.py # URL routes for the app
│ └── templates/ # HTML templates for UI rendering
│
├── media/ # Uploaded images storage
├── db.sqlite3 # Database file
├── manage.py # Django project management command
├── requirements.txt # Python dependencies
```

## **Future Scope**

- **Add product image galleries** to enrich product pages.
- Implement **pagination** and **sorting** for better UX with large catalogs.
- Integrate **AJAX** or frontend frameworks like React for dynamic filtering.
- Develop **REST APIs** using Django REST Framework for mobile and third-party access.
- Add **user authentication and authorization** to protect admin features.
- Enhance product data with **reviews, ratings, and inventory tracking**.

---

## **Author**

**Mayur Subhash Gholap**  
Mechanical Engineer | Full Stack Developer | Django & ML Enthusiast

---
