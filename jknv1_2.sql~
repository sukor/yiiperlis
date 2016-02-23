-- MySQL Workbench Forward Engineering

SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='TRADITIONAL,ALLOW_INVALID_DATES';

-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------

-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `mydb` DEFAULT CHARACTER SET utf8 ;
USE `mydb` ;

-- -----------------------------------------------------
-- Table `department`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `department` (
  `iddepartment` INT(11) NOT NULL AUTO_INCREMENT,
  `department_name` VARCHAR(45) NULL DEFAULT NULL,
  `department_address` VARCHAR(45) NULL DEFAULT NULL,
  PRIMARY KEY (`iddepartment`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `events`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `events` (
  `idevents` INT(11) NOT NULL AUTO_INCREMENT,
  `events_title` VARCHAR(45) NULL DEFAULT NULL,
  `events_date` VARCHAR(45) NULL DEFAULT NULL,
  `events_priority` VARCHAR(45) NULL DEFAULT NULL,
  `events_status` VARCHAR(45) NULL DEFAULT NULL,
  PRIMARY KEY (`idevents`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `staff`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `staff` (
  `idstaff` INT(11) NOT NULL AUTO_INCREMENT,
  `staff_name` VARCHAR(45) NULL DEFAULT NULL,
  `staff_ic` VARCHAR(45) NULL DEFAULT NULL,
  `staff_tel` VARCHAR(45) NULL DEFAULT NULL,
  `staff_address` VARCHAR(45) NULL DEFAULT NULL,
  `staff_register_date` VARCHAR(45) NULL DEFAULT NULL,
  PRIMARY KEY (`idstaff`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `branch`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `branch` (
  `idbranch` INT NOT NULL AUTO_INCREMENT,
  `branch_name` VARCHAR(45) NULL,
  `branch_aktiviti` VARCHAR(45) NULL,
  `branch_status` VARCHAR(45) NULL,
  `department_iddepartment` INT(11) NOT NULL,
  PRIMARY KEY (`idbranch`),
  INDEX `fk_branch_department1_idx` (`department_iddepartment` ASC),
  CONSTRAINT `fk_branch_department1`
    FOREIGN KEY (`department_iddepartment`)
    REFERENCES `department` (`iddepartment`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `status`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `status` (
  `idstatus` INT NOT NULL AUTO_INCREMENT,
  `status_desc` VARCHAR(45) NULL,
  `parent_id` INT NULL,
  PRIMARY KEY (`idstatus`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `job_history`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `job_history` (
  `id` INT(11) NOT NULL AUTO_INCREMENT,
  `register_date` DATE NULL DEFAULT NULL,
  `job_position` VARCHAR(45) NULL DEFAULT NULL,
  `staff_id` INT(11) NOT NULL,
  `last_department` VARCHAR(45) NULL,
  `gred` VARCHAR(45) NULL,
  `no_ic` VARCHAR(45) NULL,
  `branch_id` INT NOT NULL,
  `status_id` INT NOT NULL,
  PRIMARY KEY (`id`),
  INDEX `fk_job_history_staff1_idx` (`staff_id` ASC),
  INDEX `fk_job_history_branch1_idx` (`branch_id` ASC),
  INDEX `fk_job_history_status1_idx` (`status_id` ASC),
  CONSTRAINT `fk_job_history_staff1`
    FOREIGN KEY (`staff_id`)
    REFERENCES `staff` (`idstaff`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_job_history_branch1`
    FOREIGN KEY (`branch_id`)
    REFERENCES `branch` (`idbranch`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_job_history_status1`
    FOREIGN KEY (`status_id`)
    REFERENCES `status` (`idstatus`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `routine`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `routine` (
  `idroutine` INT(11) NOT NULL AUTO_INCREMENT,
  `routine_action` VARCHAR(45) NULL DEFAULT NULL,
  `routine_time` VARCHAR(45) NULL DEFAULT NULL,
  `staff_idstaff` INT(11) NOT NULL,
  `events_idevents` INT(11) NOT NULL,
  PRIMARY KEY (`idroutine`),
  INDEX `fk_routine_staff1_idx` (`staff_idstaff` ASC),
  INDEX `fk_routine_events1_idx` (`events_idevents` ASC),
  CONSTRAINT `fk_routine_events1`
    FOREIGN KEY (`events_idevents`)
    REFERENCES `events` (`idevents`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_routine_staff1`
    FOREIGN KEY (`staff_idstaff`)
    REFERENCES `staff` (`idstaff`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;
