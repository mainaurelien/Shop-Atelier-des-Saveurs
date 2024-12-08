### Product
- #id           --INT (pk)
- name          --TEXT (NOT NULL)
- description   --TEXT (NOT NULL)
- prix          --DECIMAL (NOT NULL)
- type          --TEXT (NOT NULL)
- stock         --INT (NOT NULL HECK (stock >= 0)  -- Contrainte pour éviter les quantités négatives)


### Category
- #id           --INT (PK)
- name          --TEXT (NOT NULL)


### Order details
- #id           --INT (PK)
- *id_order     --INT (FK REFERENCES order.id)
- *id_product   --INT (FK REFERNECES product.id)
- quantity      --INT (NOT NULL)
- unit_price    --DECIMAL (NOT NULL)


### Customer
- #id               -- INT (PK)
- firstname         -- TEXT (NOT NULL)
- lastname          -- TEXT (NOT NULL)
- email             -- TEXT (NOT NULL, UNIQUE)
- address           -- TEXT (NOT NULL)


### Order
- #id               -- INT (PK)
- date              -- DATETIME (NOT NULL)
- *id_customer      -- INT (FK REFERENCES customer.id)
- status            -- TEXT (NOT NULL)


### Product_category
- #product_id           -- INT (COMPOSITE PK) (FK REFERENCES product.id)
- #category_id          -- INT (COMPOSITE PK) (FK REFERENCES category.id)
