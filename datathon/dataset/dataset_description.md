# Data Description for the Fashion Compatibility Datathon

Below is a detailed description of the datasets you will be working with.

---
## Download data
All the data can be downloaded as a `.zip` file from the following [link](https://mng-datathon-upc.s3.eu-west-1.amazonaws.com/datathon.zip).

## 1. Product Data (`product_data.csv`)

This table contains detailed information about various fashion products.

### Fields:

1. **cod_modelo_color** - A unique identifier for a particular fashion product based on its model and color.
2. **cod_color_code** - A code indicating the specific color of the product.
3. **des_color_specification_esp** - Description of the color in Spanish.
4. **des_agrup_color_eng** - Grouped color description in English.
5. **des_sex** - Gender for which the product is intended (e.g., "Unisex", "Female", "Male").
6. **des_age** - Age group for which the product is intended (e.g., "Adult", "Child").
7. **des_line** - The line or collection to which the product belongs.
8. **des_fabric** - The fabric or material of the product.
9. **des_product_category** - Broad category of the product (e.g., "Bottoms", "Tops").
10. **des_product_aggregated_family** - An aggregated family description of the product (e.g., "Trousers & leggings").
11. **des_product_family** - Family description of the product (e.g., "Trousers", "Shirts").
12. **des_product_type** - Type of the product within its family (e.g., "Trousers", "Shirt").
13. **des_filename** - File path of the product image associated with the `cod_modelo_color`. Images can be found in the `images` folder. Image is always the frontal image of the product without a human model.

---

## 2. Outfit Data (`outfit_data.csv`)

This table is a relational table that indicates which products (identified by their `cod_modelo_color`) belong to which outfits.

### Fields:

1. **cod_outfit** - A unique identifier for a particular outfit.
2. **cod_modelo_color** - A unique identifier for a particular fashion product based on its model and color. This is used to relate the outfit with the actual product details.

---

## Relationship between the Tables:

The primary link between the `product_data` table and the `outfit_data` table is the `cod_modelo_color` field. Every `cod_modelo_color` in the `outfit_data` table can be found in the `product_data` table.

- **`product_data`**:
    - Primary Key: `cod_modelo_color`
    - Contains details about the fashion products, including its category, type, material, intended audience, and the associated image file.
- **`outfit_data`**:
    - Contains the relationships between outfits and their comprising products. 
    - By looking up a `cod_outfit`, one can find all the `cod_modelo_color` entries (products) that make up that particular outfit. Conversely, by looking up a `cod_modelo_color`, one can determine which outfits that particular product belongs to.

---

## Getting Started:

1. **Explore the Data**: Familiarize yourself with the fields in both tables and their values. This will give you insights into the kind of data you are dealing with.
2. **Linking the Data**: Use the `cod_modelo_color` field to join the tables when necessary. This will allow you to get detailed product information for each outfit.
3. **Visualizing the Data**: Utilize the `des_filename` field in the `product_data` table to view the images associated with each product. This will be essential for visually understanding the fashion products and creating compatible outfits.

Best of luck in the datathon, and happy coding!